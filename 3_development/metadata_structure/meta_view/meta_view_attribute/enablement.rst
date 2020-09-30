Условия активности
==================

Описание
--------

**Условия активности** - задают условия активности, то есть доступности  поля для редактирования в представлении.
Синтаксис условий такой же, как в `условиях отображения <meta_view_attribute/visibility.rst>`_.

Пример в JSON:
^^^^^^^^^^^^^^

.. code-block::

   {
             "caption": "Основание для условия активности",
             "type": 1,
             "property": "enablement_condition_base",
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
           },
   {
             "caption": "Поле активно, если основание заполнено",
             "type": 1,
             "property": "enablement_condition_use",
             "size": 2,
             "maskName": null,
             "mask": null,
             "mode": null,
             "fields": [],
             "hierarchyAttributes": null,
             "columns": [],
             "actions": null,
             "commands": [],
             "orderNumber": 30,
             "required": false,
             "visibility": null,
             "enablement": ".enablement_condition_base !\u003d \u0027\u0027",
             "obligation": null,
             "readonly": false,
             "selectionPaginated": true,
             "validators": null,
             "hint": null,
             "historyDisplayMode": 0,
             "tags": null
           },
           {
             "caption": "Поле активно, если в основании \u00271\u0027",
             "type": 1,
             "property": "enablement_condition_1",
             "size": 2,
             "maskName": null,
             "mask": null,
             "mode": null,
             "fields": [],
             "hierarchyAttributes": null,
             "columns": [],
             "actions": null,
             "commands": [],
             "orderNumber": 40,
             "required": false,
             "visibility": null,
             "enablement": ".enablement_condition_base \u003d\u003d \u00271\u0027",
             "obligation": null,
             "readonly": false,
             "selectionPaginated": true,
             "validators": null,
             "hint": null,
             "historyDisplayMode": 0,
             "tags": null
           }



----
