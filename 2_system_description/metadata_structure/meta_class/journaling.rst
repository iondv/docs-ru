.. role:: raw-html-m2r(raw)
   :format: html


`Оглавление </docs/ru/index.md>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Предыдущая страница: `Метка времени и пользователя создания и изменения <time_user_tracker.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Журналирование
==============

**Журналирование** - указывает на необходимость журналирования всех действий произведенных над объектом. Находится в поле ``journaling`` основной части меты класса. Значение ``true`` указывает на необходимость журналирования. Если в поле  указано значение ``false`` или отсутсвует, то журналирование изменений объекта не требуется. 

Пример:
-------

.. code-block::

   {
     "isStruct": false,
     "key": "okato",
     "semantic": "name",
     "name": "naselenniyPunkt",
     "caption": "Населенный пункт",
     "journaling": true,
     "ancestor": null,
     "container": "",
     "creationTracker": "",
     "changeTracker": "",
     "properties": []
   }

Следующая страница: `Индексация <composite_indexes.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

----

`Licence </LICENSE>`_ &ensp;  `Contact us <https://iondv.com/portal/contacts>`_ &ensp;  `English </docs/en/2_system_description/metadata_structure/meta_class/journaling.md>`_   &ensp;
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved. 
