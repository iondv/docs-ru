Поля
====

Описание
--------

**Поля** - содержат в себе атрибуты класса, объединенные, по какому-либо признаку, в группу (более подробное описание см. :doc:`Тип "Группа [0]") <type_group>`.

**Внимание:** данное свойство применяется только для атрибута типа "Группа [0]".

Пример
~~~~~~

**NB:** На форме представления, заданные атрибуты, отображаются на нижнем уровне иерархии, на верхнем находится наименование группы.

.. code-block:: json

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


----
