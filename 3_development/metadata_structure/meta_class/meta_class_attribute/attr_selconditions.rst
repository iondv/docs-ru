Условия отбора допустимых значений
==================================

Описание
--------

**Условия отбора допустимых значений** - условия, позволяющие ограничить выбор объектов по ссылке, допустимых для привязки в данном ссылочном атрибуте.

Фильтр списка допустимых значений используется в мете классов для атрибутов типа "Ссылка" и "Коллекция". Фильтром накладываются условия ограничения выборки объектов. Условия накладываются как список последовательных операций.

Доступные операции:
~~~~~~~~~~~~~~~~~~~

.. code-block:: text

   •  EQUAL: 0, // равно = 
   •  NOT_EQUAL: 1, // не равно <> 
   •  EMPTY: 2, // пусто '' или null 
   •  NOT_EMPTY: 3, // не пусто !'' или !null 
   •  LIKE: 4, // похож 
   •  LESS: 5, // меньше < 
   •  MORE: 6, // больше >
   •  LESS_OR_EQUAL: 7, // меньше или равно <=
   •  MORE_OR_EQUAL: 8, // больше или равно >=
   •  IN: 9, // элемент входит в коллекцию/массив (IN) 
   •  CONTAINS: 10 // содержит

.. code-block:: text

   module.exports = {
     AND: 0,
     OR: 1,
     NOT: 2,
     MIN: 3,
     MAX: 4,
     AVG: 5,
     SUM: 6,
     COUNT: 7
   };

Описание операций
------------------

Операции могут быть разделены на группы по наличию свойств в условии:

**Атрибут не указан в условии и условие - объект**


* nestedConditions не содержит условий

  * Операции агрегации ``AgregOpers``

    #. MIN
    #. MAX
    #. AVG
    #. SUM
    #. COUNT

* nestedConditions содержит условия

  * Логические операции сравнения вложенных условий ``BoolOpers``  

    #. OR  
    #. NOT

**Атрибут указан и условие - объект**\ : операции сравнения значения артибута в условии со значением в value


#. EMPTY
#. NOT_EMPTY
#. CONTAINS
#. EQUAL
#. NOT_EQUAL
#. LESS
#. MORE
#. LESS_OR_EQUAL
#. MORE_OR_EQUAL
#. LIKE
#. IN

**Условие в виде массива**


* Применяется логическая операция AND для сравнения результатов условий (объектов в массиве).

В операции типа ключ-выражение ключом является имя атрибута в классе ссылки или в классе коллекции. Смежные условия объединяются логической операцией «И» (если не указана другая операция) - добавляются фильтры в свойство "selConditions".

Применение операций и другие особенности
----------------------------------------

При выполнении запроса к атрибуту, необходимо использовать условие "nestedConditions". Для каждого атрибута выполняется отдельная операция. Не указывайте вложенные ссылочные атрибуты через точку в поле "property".   

Для запроса значений атрибута, которые не равны нулю, необходимо выполнить операцию ``nempty``\ , в поле "value" указываем ``null``. 

Операция **CONTAINS** применима к типам атрибута:


* строка - к строке данных применяется операция LIKE
* коллекция

  * применяется операция IN, если сравниваемое значение ``value`` является массивом и содержит хотя бы один элемент
  * происходит переход к вложенным условиям ``nestedConditions``\ , если сравниваемое значение ``value`` не является массивом или не содержит хотя бы один элемент в массиве

JSON
----

.. code-block:: json

   {
     "selConditions": [
       {
         "property": "region",
         "operation": 10,
         "value": "Хабаровский край",
         "nestedConditions": [
           {
             "property": "town",
             "operation": 0,
             "value": "г Хабаровск",
             "nestedConditions": []
           }
         ]
       }
     ]
   }

.. code-block:: json

   {
     "selConditions": [
       {

             "property": "town",
             "operation": 3,
             "value": null,
             "nestedConditions": []
           }
         ]
   }

Описание полей
--------------

.. list-table::
   :header-rows: 1

   * - Поле
     - Наименование
     - Допустимые значения
     - Описание
   * - ``"property"``
     - **Атрибут**
     - Строка, только латиница без пробелов
     - Атрибут класса ссылки, по которому производится фильтрация значений
   * - ``"operation"``
     - **Операция**
     - Код операции (см. выше)
     - Операция, согласно которой производится фильтрация
   * - ``"value"``
     - **Значение**
     - Зависит от типа операции
     - Второе значение для бинарных операций фильтрации
   * - ``"nestedConditions"``
     - **Вложенные условия отбора**
     - Объект, структура аналогична структуре самого объекта условий отбора.
     - 


Пример
~~~~~~

**Внимание**

Поле "selection_provider". См. подробнее :doc:`Список выбора допустимых значений <attr_selectionprovider>`.


* "type": "SIMPLE" - простой тип,   
* 
  "list": [] - массив допустимых значений

  .. code-block:: json

        {
          "orderNumber": 80,
          "name": "type",
          "caption": "Тип организации",
          "type": 0,
          "size": null,
          "decimals": 0,
          "nullable": true,
          "readonly": false,
          "indexed": false,
          "unique": false,
          "autoassigned": false,
          "defaultValue": null,
          "refClass": "",
          "itemsClass": "",
          "backRef": "",
          "backColl": "",
          "binding": "",
          "selConditions": [],
          "selSorting": [],
          "selectionProvider": {
            "type": "SIMPLE",
            "list": [
              {
                "key": "zakazchik",
                "value": "Заказчик"
              },
              {
                "key": "ispolnitel",
                "value": "Исполнитель"
              }
            ],
            "matrix": [],
            "parameters": [],
            "hq": ""
          },
          "indexSearch": false,
          "eagerLoading": false
        }

  
  
Пример
~~~~~~
  
В ссылочном атрибуте необходимо показать только те объекты, у которых в ссылочном классе задан атрибут "selConditions" и в поле ``property`` этого атрибута указано поле связанного класса,чьё значение в поле "value" соответствует условию "operation".

В атрибуте организация, задача показать только организации ("refClass": "organization"), у которых в поле тип ( "property": "type") равно ( "operation": 0) значению zakazchik ("value": "zakazchik").  

Все условия в ``"selConditions"`` объединяются по условию "И".  

.. code-block:: js

        {
          "orderNumber": 120,
          "name": "zakazchik",
          "caption": "Заказчик",
          "type": 13,
          "size": null,
          "decimals": 0,
          "nullable": true,
          "readonly": false,
          "indexed": false,
          "unique": false,
          "autoassigned": false,
          "defaultValue": null,
          "refClass": "organization",
          "itemsClass": "",
          "backRef": "",
          "backColl": "",
          "binding": "",
          "selConditions": [
            {
              "property": "type",
              "operation": 0,
              "value": "zakazchik",
              "nestedConditions": []
            }
          ],
          "selSorting": [],
          "selectionProvider": null,
          "indexSearch": false,
          "eagerLoading": false
        },
        {
          "orderNumber": 130,
          "name": "ispolnitel",
          "caption": "Исполнитель",
          "type": 13,
          "size": null,
          "decimals": 0,
          "nullable": true,
          "readonly": false,
          "indexed": false,
          "unique": false,
          "autoassigned": false,
          "defaultValue": null,
          "refClass": "organization",
          "itemsClass": "",
          "backRef": "",
          "backColl": "",
          "binding": "",
          "selConditions": [
            {
              "property": "type",
              "operation": 0,
              "value": "ispolnitel",
              "nestedConditions": []
            }
          ],
          "selSorting": [],
          "selectionProvider": null,
          "indexSearch": false,
          "eagerLoading": false
        }

Условия отбора допустимых значений для атрибутов с типом "Дата"
---------------------------------------------------------------

В ядре реализован атрибут контекста ``$$now``\ , возвращающий текущую дату.
``$$now`` доступен везде при задании условий.

Подробнее см. :doc:`переменные </3_development/metadata_structure/meta_variables>`.

Пример
~~~~~~

**Условие:** выводить объекты, у которых значение атрибута [dataStart] меньше текущей даты:

.. code-block:: json

   {
         "property": "dateStart",
         "operation": 5,
         "value": [
           "$$now"
         ],
         "nestedConditions": []
    }

----
