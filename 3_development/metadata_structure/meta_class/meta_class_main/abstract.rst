

Признак абстрактности класса
============================


**Признак абстрактности класса** - требуется в случае, когда необходимо по ссылке атрибута на базовый класс отображать список выбора его наследников. При формировании списка выбора классов для создания обьекта абстрактные классы не включены. Выставите ``true`` в поле "abstract".

Пример
^^^^^^

.. code-block:: js

   {
      "name": "SomeClassName",
      "abstract": true
   }

Класс становится недоступным для инициализации на уровне UI.

Пример
^^^^^^

.. code-block:: js

   {
     "isStruct": false,
     "key": [
       "id"
     ],
     "semantic": "value|[|plannedValue|](|dateStart|-|dateEnd|)",
     "name": "indicatorValueBasic",
     "version": "",
     "caption": "Значения показателей на период",
     "ancestor": null,
     "container": null,
     "creationTracker": "",
     "changeTracker": "",
     "history": 0,
     "journaling": true,
     "abstract": true,
     "compositeIndexes": [
       {
         "properties": [
           "indicatorBasic",
           "dateStart",
           "dateEnd"
         ],
         "unique": true
       }
     ],
     "properties": [
   ...


----
