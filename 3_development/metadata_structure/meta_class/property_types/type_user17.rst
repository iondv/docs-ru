Пользовательские типы
=====================

**Пользовательский тип** - ``"type": 17``\ , задает значение пользовательского типа на основе базового типа. Находится в директории ``meta``\ , ``types`` + [название типа].type.json. Используется в случаях, когда необходимо применить маску на значения определенного атрибута в различных классах.

Допустимые базовые типы
-----------------------

При создании пользовательского типа доступны следующие базовые типы:

* Строка [0]
* Целое [6]
* Действительное [7]
* Дата/Время [9]
* Десятичное [8]

Пример пользовательского типа userPassport.type.json
----------------------------------------------------

.. code-block:: json

   {
     "name": "userPassport",
     "caption": "Номер паспорта",
     "type": 0,
     "mask": "99 99 999999",
     "mask_name": "passport",
     "size": 12,
     "decimals": null
   }

Применение
----------

Пользовательские типы подключаются путем указания типа атрибута "Пользовательский [17]" - ``"type": 17`` и указанием наименования пользовательского типа в поле "refClass". 

Пользовательский тип в JSON
---------------------------

.. code-block:: json

    {
         "orderNumber": 20,
         "name": "passport",
         "caption": "Номер паспорта (Пользовательский тип [17])",
         "type": 17,
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
         "refClass": "userPassport",
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

Таким образом, при вводе значения для атрибута ``"Номер паспорта (Пользовательский тип [17])"`` будет применяться маска, заданая для типа ``"userPassport"`` по ссылке свойства ``"refClass"``. 


----
