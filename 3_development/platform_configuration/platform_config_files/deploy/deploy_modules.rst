Настройки модулей в ``deploy.json``
===================================

* :ref:`Модуль "registry" <модуль-registry>`
* :ref:`Модуль "geomap" <модуль-geomap>`
* :ref:`Модуль "gantt-chart" <модуль-gantt-chart>`
* :ref:`Модуль "report" <модуль-report>`
* :ref:`Модуль "rest" <модуль-rest>`
* :ref:`Модуль "portal" <модуль-portal>`
* :ref:`Модуль "ionadmin" <модуль-ionadmin>`
* :ref:`Модуль "dashboard" <модуль-dashboard>`
* :ref:`Модуль "diagram" <модуль-diagram>`

.. _модуль-registry:

Модуль "registry"
-----------------

**Модуль регистра (registry)** – ключевой модуль предназначенный непосредственно для работы с данными на основе структур метаданных – в том числе по ведению проектов, программ, мероприятий и др. :doc:`Подробнее о модуле регистра </4_modules/modules/registry/registry>`.

Настройка конфигурируемого сохранения файлов
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Для того, что бы задать путь сохранения файла в хранилище - указываем:

.. code-block:: text

   "modules": {
       "registry": {
         "globals": {
   ...
           "storage": {
              "className@ns":{
                  "file_attr":"/${class}/example_${attr}/${dddd}/"
              }
            },
   ...

В объекте ключом является название класса, дальше "название атрибута" : "относительный путь".

Алиасы записываются в ``${алиас}`` . Доступные алиасы:


* ``class`` - имя класс
* ``attr`` - имя атрибута
* также доступны обозначения дат из ``moment.js``

Настройка для указания количества символов для поискового запроса
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Для всего приложения - ``"listSearchMinLength"``.

.. code-block:: js

   "modules": {
     "registry": {
        "globals": {
          "listSearchMinLength": 1
         }
      }
   }

Для отдельного класса ``"minLength"``.

.. code-block:: js

   "modules": {
     "registry": {
        "globals": {
          "listSearchOptions": {
             "className@ns": {
               "*": {
                 "searchBy": [
                   "atr1"
                 ],
                 "splitBy": "\\s+",
                 "mode": [
                   "starts"
                 ],
                 "joinBy": "and",
                 "minLength": 3
               }
            }
         }
      }
   }

Настройка присвоения контейнера при создании вложенного объекта
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Для случаев, когда необходимо присваивать значение для атрибут по ссылке, не при сохранении объекта, а при создании, указываем в ``deploy.json`` приложения настройку для класса, который содержит присваемое значение:

.. code-block:: js

   "registry": {
      "globals": {
         "forceMaster": {
            "name_class@ns": true
         }
      }
    }

Пример использования генераторов последовательностей - сейчас для каждого объекта его код - это код его непосредственного контейнера плюс очередное значение счетчика последовательности привязанного к объекту-контейнеру.

Настройка жадной загрузки для печатных форм ``"skipEnvOptions"``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Подробнее о :doc:`печатных формах </3_development/functionality/functionality_files/printed_forms>`.

С помощью флага ``skipEnvOptions`` можно настроить/отключить жадную загрузку.

Пример
^^^^^^

.. code-block:: text

   ...
   "modules": {
       "registry": {
         "globals": {
   ...
           "di": {
   ...
              "export": {
                "options": {
                 "configs": {
                   "class@ns": {
                     "expertItemToDocx": {
                       "type": "item",
                       "caption": "Наименование",
                       "mimeType": "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
                       "extension": "docx",
                       "skipEnvOptions": true,
                       "preprocessor": "ion://expertItemToDocx"
                     }
                   }
                 }
                }
              }
   ...
           }
        }
      }
    }
   ...

При жадной загрузке файл создается быстро, но это не всегда может быть приемлемо.

Настройка уведомления о редактировании объекта другим пользователем
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

В настройке уведомления о редактировании объекта другим пользователем указывается время жизни для блокировки в милисекундах:

.. code-block:: js

   "modules": {
       "registry": {
         "globals": {
           "concurencyCheck": 10000
         }
       }
    }

**Компонент ConcurencyChecker**\ :

Компонент ``ConcurencyChecker`` в датасорсе хранит состояние блокировки для объектов.
Хранит следующие параметры:


* полный id объекта (класс@id), 
* датавремя блокировки (blockDate), 
* заблокировавший пользователь.

Компонент создает состояния блокировки, при этом запускается таймер, по которому запись о блокировке удаляется по истечении таймаута. Если на момент срабатывания таймера запись оказывается еще актуальной (обновляли blockDate), то запись не удаляется, а таймер обновляется.

**Логика в контроллере view**\ :

Читаем из сетингов настройку *registry.concurencyCheck* (таймаут блокировки в секундах).

Если она больше 0, обращаемся к ``ConcurencyCheker`` - проверяем состояние блокировки. 

Если не найдено (либо просрочена - blockDate < now() - registry.concurencyCheck), то через чекер записываем новую блокировку от имени текущего пользователя. Если найдена живая блокировка - передаем в шаблон информацию о блокировке, которую отображаем на форме и отображаем форму в режиме для чтения (\ ``globalReadOnly``\ ).

Дополнительный контроллер ``concurencyState``\ , который принимает id объекта и проверяет его состояние блокировки. Если объект не заблокирован (нет блокировки, либо она просрочена), то блокирует объект от имени текущего пользователя. Если объект заблокирован текущим пользователем, обновляет *blockDate* на *new Date()*. Возвращает состояние блокировки.

**Поведение формы объекта**\ :

Если в шаблон передана инфа о блокировке, то добавляется скрипт, который периодически (с периодом ``registry.concurencyCheck/2``\ ) обращается к контроллеру ``concurencyState``.

Если в ответ приходит информация о блокировке другим пользователем - она отображается (обновляем сообщение), если произошел перехват блокировки текущим пользователем - форма перезагружается (она при этом отображается в режиме для редактирования).

Подключение ресурсов в проекте для оформления
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Это имеет отношение, например к группам в специальном стиле - чтобы не подключать ресурсы через изменения шаблонов модуля - необходимо их подключить в приложении.

.. code-block:: js

           "statics": {
             "geoicons": "applications/khv-svyaz-info/icons"
           }

Все, что внутри директории ``icons`` доступно по ссылке ``registry/geoicons``.

Настройка формы указания параметров экспорта (для печатных форм)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Пример с параметрами в ``params``\ :

.. code-block:: text

   ...
           "di": {
             "pmListToDocx": {
               "module": "modules/registry/export/listToDocx",
               "initMethod": "init",
               "initLevel": 0,
               "options": {
                 "tplDir": "applications/project-management/export/item2",
                 "log": "ion://sysLog"
               }
             }
   ...
             "export": {
               "options": {
                 "configs": {
                   "evaluationPerform@project-management": {
                     "rating": {
                       "caption": "Оценка деятельности исполнителя и соисполнителей проекта",
                       "mimeType": "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
                       "extension": "docx",
                       "type": "list",
                       "query": {
                         "filter": {
                           "and": [
                             {
                               "eq": [
                                 "$basicObjPerform",
                                 ":project"
                               ]
                             },
                             {
                               "gte": [
                                 "$date",
                                 ":since"
                               ]
                             },
                             {
                               "lte": [
                                 "$date",
                                 ":till"
                               ]
                             }
                           ]
                         }
                       },
                       "params": {
                         "project": {
                           "caption": "Проект",
                           "type": "reference",
                           "className": "project@project-management"
                         },
                         "since": {
                           "caption": "Период с",
                           "type": "date",
                           "default": "$monthStart"
                         },
                         "till": {
                           "caption": "Период по",
                           "type": "date",
                           "default": "$monthEnd"
                         }
                       },
                       "eagerLoading": [
                         "ownOrg",
                         "basicObjs"
                       ],
                       "preprocessor": "ion://pmListToDocx"
                     }
                   }
   ...

Настройка параметров поиска в списке объектов
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Функционал позволяет на уровне класса определять, как ищем объекты класса из представления списка: по вхождению слов или полные слова, по отдельным атрибутам или по указанным атрибутам в списке с параметрами поиска через пробел.

Формат и доступные операции:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: text

   "listSearchOptions": {
       "person@khv-childzem": {...} // для класса
          "khv-childzem@person": {...} // только в узле навигации person
         "*": {...} // везде по умолчанию
   }

вместо ``...`` подставляем атрибуты и задаем операции для поиска, например:

.. code-block:: js

           "searchBy": [ // атрибуты по которым ищем, по умолчанию то, что выводится в колонках
            "surname",
            "name",
            "patronymic"
          ],
          "splitBy": "\\s+", // разбивать поисковую фразу регуляркой, части сопоставить с атрибутами
          "mode": ["starts", "starts", "starts"], // режимы сопоставления - в данном случае "начинается с" (доступны like, contains, starts, ends)
          "joinBy": "and" // режим объединения условий на атрибуты (по умолчанию or)

.. _настройка-иерархического-представления-для-коллекций:

Настройка иерархического представления для коллекций
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

**Иерархическое представление коллекций**\ - отображает коллекции, в которых элементы связаны друг с другом в виде иерархического справочника. В библиотеке ``viewlib`` реализован кастомный контроллер, возвращающий в формате ``TreeGrid`` очередной уровень иерархии.

Пример
^^^^^^

.. code-block:: text

   "treegridController": {
               "module": "applications/viewlib/lib/controllers/api/treegrid",
               "initMethod": "init",
               "initLevel": 0,
               "options": {
                 "module": "ion://module",
                 "logger": "ion://sysLog",
                 "securedDataRepo": "ion://securedDataRepo",
                 "metaRepo": "ion://metaRepo",
                 "auth": "ion://auth",
                 "config": {
                   "*": {
                     "project@project-management":{
                       "roots":[{
                         "property": "name",
                         "operation": 1,
                         "value": [null],
                         "nestedConditions": []
                       }],
                       "childs":["stakeholders", "basicObjs"]
                     },
                     "governmentPower@project-management": {
                       "roots":[],
                       "childs":null,
                       "override": {
                         "descript": "url"
                       }
                     },
                     "object@project-management": {
                       "roots":[],
                       "childs":null
                     },
                     "event@project-management": {
                       "roots":[],
                       "childs":null
                     }
                   }
                 }
               }
             }
   ...

Поле ``config`` - в нем все настройки:


* первый ключ это навигационная нода (в данном примере "*" значит распространяется на все ноды), 
* потом идут классы, у классов ``roots`` - это какие объекты этого класса вытаскивать в качестве корневых (используются "conditions"),
* ``childs`` - это атрибуты класса из которых доставать иерархию.

Настройка текстового поиска в глубину по ссылочным атрибутам
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

``searchByRefs`` - это массив настроек, для обозначения иерархии классов. Можно сопоставлять с несколькими классами.

Пример
^^^^^^

.. code-block:: js

   "family@khv-childzem": {
               "*": {
                 "searchByRefs":[
                   {
                     "class": "person@khv-childzem",
                     "idProperties": ["famChilds", "famParentMale", "famParentFemale"],
                     "searchBy": [
                       "surname",
                       "name",
                       "patronymic"
                     ],
                     "splitBy": "\\s+",
                     "mode": [
                       "starts",
                       "starts",
                       "starts"
                     ],
                     "joinBy": "and"
                   }
                 ]
               }
             }

.. _модуль-geomap:

Модуль "geomap"
---------------

**Геомодуль (geomap)** – предназначен для визуализации сведений и данных, имеющих географическую привязку. 

Настройка иконки приложения
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Логотип для модуля описывается через стандартный механизм статичных маршрутов:

.. code-block:: json

   {
     "modules": {
       "geomap": {
         "statics":[{"path":"applications/khv-svyaz-info/icons", "name":"icons"}],
         "logo": "icons/logo.png"
       }
     }
   }

Настройка скрытия шапки и бокового меню
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Пример:
^^^^^^^

.. code-block:: js

   "geomap": {
      "globals": {
         "hidePageHead": true, //отобразить шапку
         "hidePageSidebar": false, //скрыть боковое меню 
         ...
       }
    }

.. _модуль-gantt-chart:

Модуль "gantt-chart"
--------------------

**Модуль диаграм ганта (gantt-chart)** – модуль, предназначенный для вывода специфичных типов иерархических данных имеющих даты. :doc:`Подробнее о модуле диаграм ганта </4_modules/modules/gantt-chart>`.

Настройка шкалы времени
~~~~~~~~~~~~~~~~~~~~~~~

Шкала времени настраивается посредством настройки "Шаг" в модуле Гаанта.
В преконфигурации "Шаг" задается через параметр ``step``\ :

.. code-block:: json

   {
     "unit": "year",
     "step": 5
   }

Пример
^^^^^^

.. code-block:: text

   ...
      "gantt-chart": {
         "globals": {
           "config": {
   ...
             "preConfigurations": {
   ...
               "config3": {
                 "caption": "Третья конфигурация",
                 "showPlan": true,
                 "units": "year",
                 "step": 5,
                 "days_mode": "full",
                 "hours_mode": "full",
                 "columnDisplay": {
                   "text": true,
                   "owner": true,
                   "priority": true
                 },
                 "filters": {
                   "priority": "Обычный"
                 }
               }
             }
   ...
           }
         }
       }

.. _модуль-report:

Модуль "report"
---------------

**Модуль отчетов (report)** – модуль предназначенный для формирования, на основе специальных метаданных – аналитических отчетов и справочной информации. Расчеты могут выполняться по расписанию или быть инициированы оператором. :doc:`Подробнее о модуле отчетов </4_modules/modules/report/report>`.

.. code-block:: js

   "report": {
         "globals": {
           "namespaces": {
             "project-management": "Проектное управление"
           },
           "defaultNav": {
             "namespace": "project-management",
             "mine": "projects",
             "report": "roadmap"
           },
           "mineBuilders": {
             "project-management": {
               "test": {
                 "projects": "mineBuilder"
               },
               "projects": {
                 "indicatorAll": "mineBuilder"
               }
             }
           },
           "di": {},
           "statics": {
             "common-static": "applications/project-management/templates/static"
           },
           "logo": "common-static/logo.png"
         },
         "import": {
           "src": "applications/project-management/bi",
           "namespace": "project-management"
         }
       }

.. _модуль-rest:

Модуль "rest"
-------------

**Модуль REST-сервисов** – модуль предназначенный для осуществления интеграции по формату REST. Используется для предоставления данных для модуля портала. :doc:`Подробнее о модуле REST </4_modules/modules/rest/rest>`.

.. code-block:: js

    "rest": {
         "globals": {
           "di": {}
         }
       },

.. _модуль-portal:

Модуль "portal"
---------------

**Модуль портала (portal)** – модуль, предназначенный для отображения произвольных шаблонов данных. :doc:`Подробнее о модуле портала </4_modules/modules/portal>`

.. code-block:: js

   "portal": {
         "import": {
           "src": "applications/project-management/portal",
           "namespace": "project-management"
         },
         "globals": {
           "portalName": "pm",
           "needAuth": true,
           "default": "index",
           "theme": "project-management/portal",
           "templates": [
             "applications/project-management/themes/portal/templates"
           ],
           "statics": {
             "pm": "applications/project-management/themes/portal/static"
           },
           "pageTemplates": {
             "navigation": {
               "index": "pages/index"
             }
           }
         }
       }

.. _модуль-ionadmin:

Модуль "ionadmin"
-----------------

**Модуль администрирования (ionadmin)** – используется для назначения прав, управления задачами по расписанию и другими административными задачами. :doc:`Подробнее о модуле администрирования </4_modules/modules/admin/admin>`.

Скрытие ролей в админе от назначения пользователю
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Для ролей, которые должны быть скрыты в админе от назначения пользователю, в деплое приложения прописываем фильтры на основе регулярных выражений, по которым такие роли и будут определятся.

.. code-block:: js

   "ionadmin": {
         "globals": {
           "securityParams": {          
             "hiddenRoles": [
               "^somePrefix_"
             ]
           }
         }
       }

Настройка скрытия модуля в системном меню
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Для скрытия модуля из системного меню проекта присваиваем этому модулю, в файле ``deploy.json``\ , значение *null*\ , например ``"ionadmin": null``.

.. code-block:: js

   {
     "namespace": "project-management",
     "parametrised": true, //
     "globals": {
       "moduleTitles": {
         "registry": {
           "description": "Проектное управление",
           "order": 10,
           "skipModules": true
         }
         "ionadmin": null
       }

.. _модуль-dashboard:

Модуль "dashboard"
------------------

**Модуль дашбоарда (dashboard)** – модуль предназначенный для выведения краткой информации в виде блоков. :doc:`Подробнее о модуле дашбоарда </4_modules/modules/dashboard>`.

Для того что бы данные из меты загружались в модуль "dashboard", необходимо в файле конфигурации приложения
``deploy.json`` добавить следующую секцию, в раздел ``"modules"``\ :

.. code-block:: js

      "dashboard": {
         "globals": {
           "namespaces": {
             "project-management": "Проектное управление"
           },
           "root": {
             "project-management": "applications/project-management/dashboard"
           }
         }
       }

.. _модуль-diagram:

Модуль "diagram"
----------------

.. code-block:: js

   "diagram": {
         "globals": {
           "config": {
             "org1": {
               "caption": "Организационная структура",
               "edit": true,
               "showSections": false,
               "relations": {
                 "className": "organization@project-management",
                 "title": "name",
                 "text": "address",
                 "img": "",
                 "filter": [
                   {
                     "property": "headOrg",
                     "operation": 0,
                     "value": [
                       null
                     ],
                     "nestedConditions": []
                   }
                 ],
                 "children": [
                   {
                     "className": "branchOrg@project-management",
                     "property": "branch",
                     "title": "name",
                     "text": "address",
                     "children": [
                       {
                         "className": "branchOrg@project-management",
                         "property": "branch",
                         "children": []
                       }
                     ]
                   }
                 ]
               }
             }
           }
         }
       }

Полный пример файла :doc:`deploy.json <deploy_ex>`

----
