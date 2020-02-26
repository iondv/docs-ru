.. role:: raw-html-m2r(raw)
   :format: html


`Оглавление </docs/ru/index.md>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Предыдущая страница: `Условия отбора допустимых значений <atr_selconditions.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Сортировка выборки допустимых значений
======================================

Описание
--------

**Сортировка выборки допустимых значений** - задается при создания сущности в поле ``"selSorting"``  и представляет собой фильтр, который задает способ сортировки объектов. Применяется для атрибутов типа  ``"Ссылка"``.

Доступные типы сортировки:
^^^^^^^^^^^^^^^^^^^^^^^^^^

•  Сортировка по возрастанию\ :raw-html-m2r:`<br>`
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


Следующая страница: `Список выбора допустимых значений <atr_selectionprovider.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

----

`Licence </LICENSE>`_ &ensp;  `Contact us <https://iondv.com/portal/contacts>`_ &ensp;  `English </docs/en/2_system_description/metadata_structure/meta_class/atr_selconditions.md>`_   &ensp;
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved. 
