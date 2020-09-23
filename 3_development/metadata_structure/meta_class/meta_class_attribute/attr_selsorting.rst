Сортировка выборки допустимых значений
======================================

Описание
--------

**Сортировка выборки допустимых значений** - задается при создания сущности в поле ``"selSorting"``  и представляет собой фильтр, который задает способ сортировки объектов. Применяется для атрибутов типа  ``"Ссылка"``.

Доступные типы сортировки:
^^^^^^^^^^^^^^^^^^^^^^^^^^

•  Сортировка по возрастанию
•  Сортировка по убыванию

JSON
----

.. code-block::

   {
         "orderNumber": 20,
         "name": "ref",
         "caption": "Ссылка",
         "type": 13,
         "size": null,
         "decimals": 0,
         "allowedFileTypes": null,
         "maxFileCount": 0,
         "nullable": true,
         "readonly": false,
         "indexed": false,
         "unique": false,
         "autoassigned": false,
         "hint": null,
         "defaultValue": null,
         "refClass": "selSortingCatalog@develop-and-test",
         "itemsClass": "",
         "backRef": "",
         "backColl": "",
         "binding": "",
         "semantic": null,
         "selConditions": [],
         "selSorting": [
           {
             "property": "string",
             "mode": 1
           }
         ],

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
     - Атрибут, по которому будет производится сортировка.
   * - ``"mode"``
     - **Порядок сортировки**
     - *0 - по возрастанию*
     - Порядок сортировки
   * - 
     - 
     - *1 - по убыванию*
     -




----
