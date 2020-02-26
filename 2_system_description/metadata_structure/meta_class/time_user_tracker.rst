.. role:: raw-html-m2r(raw)
   :format: html


`Оглавление </docs/ru/index.md>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Предыдущая страница: `Наследование <ancestor.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Метки времени создания и изменения
==================================

Речь идет о следующих полях общей части меты классов:


#. ``"creationTracker"`` - **Метка времени создания**\ :  Позволяет сохранять в классе дату/время создания объекта, требует наличия соответствующего атрибута класса, ``"name"`` которого и вносится в данное поле.
#. ``"changeTracker"`` - **Метка времени изменения**\ : Позволяет сохранять в классе дату/время изменения объекта, требует наличия соответствующего атрибута класса, ``"name"`` которого и вносится в данное поле.

Пример:
^^^^^^^

.. code-block::

   {
     "isStruct": false,
     "key": "id",
     "semantic": "rtrs",
     "name": "digitTv",
     "caption": "Цифровое ТВ",
     "ancestor": null,
     "container": null,
     "creationTracker": "createDate",
     "changeTracker": "modifeDate",
     "properties": [
       {
         "orderNumber": 60,
         "name": "createDate",
         "caption": "Метка времени создания",
         "type": 9,
         "size": null,
         "decimals": 0,
         "nullable": false,
         "readonly": false,
         "indexed": false,
         "unique": true,
         "autoassigned": true,
         "defaultValue": null,
         "refClass": "",
         "itemsClass": "",
         "backRef": "",
         "backColl": "",
         "binding": "",
         "selConditions": [],
         "selSorting": [],
         "selection_provider": null,
         "indexSearch": false,
         "eagerLoading": false
       },
       {
         "orderNumber": 70,
         "name": "modifeDate",
         "caption": "Метка времени изменения",
         "type": 9,
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
         "selection_provider": null,
         "indexSearch": false,
         "eagerLoading": false
       }
   ]

Метки пользователя создавшего и измененившего объект
====================================================


#. 
   ``"creatorTracker"`` - **Метка пользователя создавшего**\ :  Позволяет сохранять в классе имя пользователя, создавшего объект, требует наличия соответствующего атрибута класса, ``"name"`` которого и вносится в данное поле.

#. 
   ``"editorTracker"`` - **Метка пользователя изменившего**\ : Позволяет сохранять в классе имя пользователя, изменившего объект, требует наличия соответствующего атрибута класса, ``"name"`` которого и вносится в данное поле.

.. code-block:: json

   {
     "isStruct": false,
     "key": [
       "guid"
     ],
     "semantic": "name",
     "name": "basicObj",
     "abstract": true,
     "version": "31",
     "caption": "Учетный объект",
     "ancestor": null,
     "cacheDependencies": [
       "basicObj"
     ],
     "container": null,
     "creatorTracker": "creator",
     "editorTracker": "editor",
     "history": 0,
     "journaling": true,
     "compositeIndexes": null,
     "properties": [
       ...
       {
         "orderNumber": 20,
         "name": "creator",
         "caption": "Метка пользователя, создавшего объект",
         "type": 18,
         "size": null,
         "decimals": 0,
         "allowedFileTypes": null,
         "maxFileCount": 0,
         "nullable": true,
         "readonly": false,
         "indexed": false,
         "unique": false,
         "autoassigned": true,
         "hint": "",
         "defaultValue": null,
         "refClass": "",
         "itemsClass": "",
         "backRef": "",
         "backColl": "",
         "binding": "",
         "semantic": null,
         "selConditions": [],
         "selSorting": [],
         "selectionProvider": null,
         "indexSearch": false,
         "eagerLoading": false,
         "formula": null
       },
       {
         "orderNumber": 30,
         "name": "editor",
         "caption": "Метка пользователя, изменившего объект",
         "type": 18,
         "size": null,
         "decimals": 0,
         "allowedFileTypes": null,
         "maxFileCount": 0,
         "nullable": true,
         "readonly": false,
         "indexed": false,
         "unique": false,
         "autoassigned": true,
         "hint": "",
         "defaultValue": null,
         "refClass": "",
         "itemsClass": "",
         "backRef": "",
         "backColl": "",
         "binding": "",
         "semantic": null,
         "selConditions": [],
         "selSorting": [],
         "selectionProvider": null,
         "indexSearch": false,
         "eagerLoading": false,
         "formula": null
       }
     ],
     "metaVersion": "2.0.61"

Следующая страница: `Журналирование изменений <journaling.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

----

`Licence </LICENSE>`_ &ensp;  `Contact us <https://iondv.com/portal/contacts>`_ &ensp;  `English </docs/en/2_system_description/metadata_structure/meta_class/time_user_tracker.md>`_   &ensp;
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved. 
