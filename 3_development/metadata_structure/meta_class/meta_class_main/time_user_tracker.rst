Метки времени создания и изменения
==================================

Речь идет о следующих полях общей части меты классов:

#. ``"creationTracker"`` - **Метка времени создания**\ :  позволяет сохранять в классе дату/время создания объекта, требует наличия соответствующего атрибута класса, ``"name"`` которого и вносится в данное поле.
#. ``"changeTracker"`` - **Метка времени изменения**\ : позволяет сохранять в классе дату/время изменения объекта, требует наличия соответствующего атрибута класса, ``"name"`` которого и вносится в данное поле.

Пример
------

.. code-block:: js

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
   }

Метки пользователя создавшего и измененившего объект
====================================================

#. 
   ``"creatorTracker"`` - **Метка пользователя создавшего**\ :  позволяет сохранять в классе имя пользователя, создавшего объект, требует наличия соответствующего атрибута класса, ``"name"`` которого и вносится в данное поле.

#. 
   ``"editorTracker"`` - **Метка пользователя изменившего**\ : позволяет сохранять в классе имя пользователя, изменившего объект, требует наличия соответствующего атрибута класса, ``"name"`` которого и вносится в данное поле.

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
	}


----

