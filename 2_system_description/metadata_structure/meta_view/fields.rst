.. role:: raw-html-m2r(raw)
   :format: html


`Оглавление </docs/ru/index.md>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Предыдущая страница: `Маски <mask.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Поля
====

Описание
--------

**Поля** - содержат в себе атрибуты класса, объединенные, по какому-либо признаку, в группу (более подробное описание см. `Тип "Группа [0]") <type_group.md>`_.

**Внимание:** данное свойство применяется только для атрибута типа "Группа [0]".

Пример
^^^^^^

**NB:** На форме представления, заданные атрибуты, отображаются на нижнем уровне иерархии, на верхнем находится наименование группы.

.. code-block::

   {
     "tabs": [
       {
         "caption": "",
         "fullFields": [
           {
             "caption": "nameGroup",
             "type": 0,
             "property": "",
             "size": 2,
             "maskName": null,
             "mask": null,
             "mode": null,
             "fields": [
               {
                 "caption": "atr1",
                 "type": 1,
                 ...
               },
               {
                 "caption": "atr2",
                 "type": 1,
                 ...
               }
         ]
       }
         ],
         "shortFields": []
       }
     ]
   }

Следующая страница: `Действия <commands.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

----

`Licence </LICENSE>`_ &ensp;  `Contact us <https://iondv.com/portal/contacts>`_ &ensp;  `English </docs/en/2_system_description/metadata_structure/meta_view/fields.md>`_   &ensp;
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved. 
