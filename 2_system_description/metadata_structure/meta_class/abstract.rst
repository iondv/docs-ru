.. role:: raw-html-m2r(raw)
   :format: html


Признак абстрактности класса
============================
:doc:`Оглавление <../../../index>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Предыдущая страница: :doc:`Семантика <semantic>`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

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

Следующая страница: :doc:`Версионирование <metaversion>`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

----

`License <https://github.com/iondv/framework/blob/master/LICENSE>`_                                        `Contact us <https://iondv.com/portal/contacts>`_                                         `English <https://iondv.readthedocs.io/en/latest/index.html>`_
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved. 
