Глобальные настройки в ``deploy.json``
======================================

Глобальные настройки конфигурации приложения включает в себя следующие разделы:


* Пространство имен приложния ``"namespace"``
* Параметризация ``"parametrised"``
* Путь к шаблонам ``"theme"``
* Время кеширования и другие параметры для статичных файлов https://expressjs.com/en/4x/api.html#express.static ``"staticOptions"`` (работает при NODE_ENV=production)
* Наименование вкладки в браузере\ ``"pageTitle"``
* Модули приложения ``"moduleTitles"`` -  :ref:`перейти <модули-приложения>`
* Настройка отображения общего системного меню для всех модулей проекта ``"explicitTopMenu"`` - :ref:`перейти <настройка-отображения-общего-системного-меню-для-всех-модулей-проекта>`
* Переопределение настроек хранилища сессий ``"sessionHandler"``
* ``"actualAclProvider"``
* ``"aclProvider"``
* Настройка HTML атрибутов для отображения и сохранения картинок в атрибуте ``"fileStorage"`` - :ref:`перейти <настройка-html-атрибутов-для-отображения-и-сохранения-картинок-в-атрибуте>`
* Настройки отображения имени пользователя и аватара во всех модулях проекта ``"customProfile"``  - :ref:`перейти <настройки-отображения-имени-пользователя-и-аватара-во-всех-модулях-проекта>`
* Настройка глубины жадной загрузки ``"dataRepo"`` - :ref:`перейти <настройка-глубины-жадной-загрузки>`
* ``"accounts"``
* ``"securedDataRepo"``
* ``"ldap"``
* ``"auth"``
* ``"sendmail"``
* ``"nodemailer"``
* ``"emailNotifier"``
* ``"notifier"``
* ``"eventNotifier"``
* Настройки интеграции с календарем ``"icsMailer"`` - :ref:`перейти <настройки-интеграции-с-календарем>`
* ``"recache"``
* ``"fact-creator"``
* ``"report-builder"``
* ``"projectReportCreator"``

Структура которых строится следующим образом: 

.. code-block:: text

   {
     "namespace": "...",
     "parametrised": true,
     "globals": {
       "theme": "...",
       "staticOptions": {...},
       "pageTitle": "...",
       "moduleTitles": {...},
       "explicitTopMenu": [...],
       "plugins": {
         "sessionHandler": {...},
         "actualAclProvider": {...},
         "aclProvider": {...},
         "fileStorage": {...},
         "customProfile": {...},
         "dataRepo": {...},
         "accounts": {...},
         "securedDataRepo": {...},
         "ldap": {...},
         "auth": {...},
         "sendmail": {...},
         "nodemailer": {...},
         "emailNotifier": {...},
         "notifier": {...},
         "eventNotifier": {...},
         "icsMailer": {...}
       },
       "jobs": {
         "recache": {...},
         "fact-creator": {...},
         "report-builder": {...},
         "projectReportCreator": {...}
       }
     }
   }

.. _модули-приложения:

Модули приложения
-----------------

Для свойства необходимо задать модули, которые будут использованы в приложении в поле "moduleTitles". Также эти же модули будут отображаться в системном меню.

.. code-block:: json

   {
     "namespace": "crm",
     "globals": {
       "moduleTitles": {
         "registry": "Тех. поддержка",
         "report": "Отчеты"
       }
     }
   }

Настройка скрытия модуля в системном меню
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Для скрытия модуля из системного меню проекта присваиваем этому модулю, в файле ``deploy.json``\ , значение *null*\ , например ``"ionadmin": null``.

.. code-block:: json

   {
     "namespace": "project-management",
     "parametrised": true,
     "globals": {
       "moduleTitles": {
         "registry": {
           "description": "Проектное управление",
           "order": 10,
           "skipModules": true
         },
         "ionadmin": null
       }
     }
   }

.. _настройка-отображения-общего-системного-меню-для-всех-модулей-проекта:

Настройка отображения общего системного меню для всех модулей проекта
---------------------------------------------------------------------

Для того, чтобы в системном меню отображался одинаковый набор пунктов, не зависимо от того, на странице какого модуля находишься - необходимо в ``deploy.json`` файле проекта задать ``"explicitTopMenu"`` на глобальном уровне, с сохранением возможности переопределять ``"explicitTopMenu"`` в ``registry``.

Пример
~~~~~~

.. code-block:: js

   "globals": {
       "explicitTopMenu": [
         {
           "id":"mytasks",
           "url": "/registry/project-management@indicatorValue.all",
           "caption":"Мои задачи"
         },
         {
           "id":"projectmanagement",
           "url": "/registry/project-management@project",
           "caption":"Проектное управление"
         },
         {
           "type": "system",
           "name": "gantt-chart"
         },
         {
           "type": "system",
           "name": "portal"
         },
         {
           "type": "system",
           "name": "geomap"
         },
         {
           "type": "system",
           "name": "report"
         },
         {
           "id":"distionary",
           "url": "/registry/project-management@classification.okogu",
           "caption":"Справочники"
         },
         {
           "id":"mark",
           "url": "/registry/project-management@person",
           "caption":"Прогресс-индикатор"
         }
       ],

Описание полей
^^^^^^^^^^^^^^

* ``"id"`` - идентификатор секции навигации
* ``"url"`` - url секции навигации
* ``"caption"`` - наименование секции навигации
* ``"name"`` - системное наименование модуля

Поле "plugins"
--------------

В данном поле задаются настройки, которые позволяют дополнительно расширить возможности приложения. 

.. _настройка-html-атрибутов-для-отображения-и-сохранения-картинок-в-атрибуте:

Настройка HTML атрибутов для отображения и сохранения картинок в атрибуте
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

``"plugins":{``

.. code-block:: js

   "fileStorage": {
       "module": "core/impl/resource/OwnCloudStorage",
       "options": {
         "url": "https://owncloud.iondv.ru/",
         "login": "api",
         "password": "apiapi"
       }
   }

.. code-block:: js

   "htmlFiles": {
       "module": "core/impl/resource/FsStorage",
       "initMethod":"init",
       "initLevel": 3,
       "options": {
         "storageBase": "./htmlFiles",
         "urlBase": "/htmlFiles",
         "dataSource": "ion://Db",
         "log": "ion://sysLog",
         "app": "ion://application",
         "auth": "ion://auth"
       },
       "htmlImages": {
           "module": "core/impl/resource/ImageStorage",
           "initMethod": "init",
           "initLevel": 3,
           "options": {
             "fileStorage": "ion://htmlFiles",
             "app": "ion://application",
             "auth": "ion://auth",
             "log": "ion://sysLog",
             "urlBase": "/htmlFiles",
             "thumbnails": {
               "small": {
                 "width": 100,
                 "height": 100
               }
             }
           }
       }
   }

``"modules": {``
``"registry": {``
``"globals":``

.. code-block:: js

   {
       "refShortViewDelay": 1000, // количество миллисекунд до появления окна с инфо. Если не указан или 0, или нет shortView представления, то окно не выводится
       "defaultImageDir": "images",
       "contentImageStorage": "htmlImages"
   }

.. _настройки-отображения-имени-пользователя-и-аватара-во-всех-модулях-проекта:

Настройки отображения имени пользователя и аватара во всех модулях проекта
--------------------------------------------------------------------------

Для задания аватара через деплой прописываем связь с изображением.
Аватар будет браться из соответствующего атрибута класса, объект которого привязан к текущему системному пользователю.

Пример
~~~~~~

.. code-block:: js

   "customProfile": {
     "module": "lib/plugins/customProfile",
     "initMethod": "inject",
     "options": {
       "auth": "ion://auth",
       "metaRepo": "ion://metaRepo",
       "dataRepo": "ion://dataRepo",
       "propertyMap": {
         "person@project-management": {
           "filter": "user",
           "properties": {
             "avatar": "foto"
           }
         }
       }
     }
   }

.. _настройка-глубины-жадной-загрузки:

Настройка глубины жадной загрузки
---------------------------------

.. code-block:: js

   "dataRepo": {
     "options": {
       "maxEagerDepth": 4
     }
   }

.. _настройки-интеграции-с-календарем:

Настройки интеграции с календарем
---------------------------------

Интеграция осуществляется следующим образом: модуль по событию отправляет письмо с прикрепленным ``ics-файлом``\ , в котором указано событие *iCalendar*.  *Outlook* воспринимает такое письмо как приглашение на собрание. *Яндекс* тоже добавляет собрание в календарь. 

Конфигурации модуля:

.. code-block:: js

   "icsMailer": {
     "module": "applications/extensions/lib/icsMailer",
     "initMethod": "init",
     "initLevel": 2,
     "options": {
       "dataRepo": "ion://dataRepo",
       "transport": {...}, //Настройки smtp-сервера
       "defaults": {...}, //Общий настройки всех писем
       "listeners": [
         {
           "component": //Ссылка на слушаемый компонент
           "events": {
             "...": {// Идентификатор события
               "calendar": {...}, //Настройки календаря, несущего событие и передаваемого в ics-вложении
               "event": {...}, //Настройки VEVENT, передаваемого в ics-вложении
               "filename": "...", //Имя вложенного ics-файла
               "letter": {...} //Настройки письма, отправляемого по событию.
             }
           }
         }
       ]
     }
   }


* Подробности настройки `transport и defaults <https://nodemailer.com/smtp/>`_.
* Подробности настройки `letter <https://nodemailer.com/message/>`_
* Подробности настройки `calendar <https://www.npmjs.com/package/ical-generator#calendar>`_
* Подробности настройки `event <https://www.npmjs.com/package/ical-generator#event>`_

Для настроек *letter*\ , *event*\ , *filename* и *calendar* предусмотрена возможность использовать данные из объекта события, указывая имена свойств через точку ``refAttr.stringAttr``\ , либо обернув эту конструкцию в ``${refAttr.stringAttr}`` когда необходимо использовать шаблон.

Полный пример файла :doc:`deploy.json <deploy_ex>`

----
