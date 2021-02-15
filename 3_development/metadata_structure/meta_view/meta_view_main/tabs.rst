Вкладки
=======

**Вкладки** - задаются в представлении создания и редактирования и используются для разбиения атрибутов класса по отдельным вкладкам на форме.

Структура:
----------

.. code-block:: json

   {
     "tabs": [
       {
          "caption": "1",
             "fullFields": [],
             "shortFields": []
       },
       {
          "caption": "2",
             "fullFields": [],
             "shortFields": []
       }
     ]
   }

где, ``caption`` - наименование вкладки и ``fullFields`` - атрибуты на вкладке

Пример
------

.. code-block:: text

   {
     "tabs": [
       {
         "caption": "Первая вкладка",
         "fullFields": [
           {
             "caption": "Первый атрибут на первой вкладке",
             "type": 1,
             "property": "tab_1_1",
             "size": 2,
             "maskName": null,
             "mask": null,
             "mode": null,
             "fields": [],
             "hierarchyAttributes": null,
             "columns": [],
             "actions": null,
             "commands": [],
             "orderNumber": 10,
             "required": false,
             "visibility": null,
             "enablement": null,
             "obligation": null,
             "readonly": false,
             "selectionPaginated": true,
             "validators": null,
             "hint": null,
             "historyDisplayMode": 0,
             "tags": ["css:background-color:#AFFFAF"]
           },
           {
             "caption": "Второй атрибут на первой вкладке",
             "type": 1,
             "property": "tab_1_2",
             "size": 2,
             "maskName": null,
             "mask": null,
             "mode": null,
             "fields": [],
             "hierarchyAttributes": null,
             "columns": [],
             "actions": null,
             "commands": [],
             "orderNumber": 20,
             "required": false,
             "visibility": null,
             "enablement": null,
             "obligation": null,
             "readonly": false,
             "selectionPaginated": true,
             "validators": null,
             "hint": null,
             "historyDisplayMode": 0,
             "tags": null
           }
         ]

----
