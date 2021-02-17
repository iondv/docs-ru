Обновление объекта: методы PATCH и PUT
======================================

**Обновление объекта** осуществляется методом ``PATCH`` или ``PUT``\ , при этом указывается код класса с нейспейсом и значение ключа объекта,
например ``rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b``. Сам объект передается в теле запроса в формате json с обязательным указанием в заголовке типа содержания json ``Content-Type:application/json``.

Пример:

.. code-block:: bash

   curl -X PATCH -u demo@local:demo-ion -H "Content-Type:application/json" -d '{"string_text": "NEW Example", "string_miltilinetext": "NEW Example", "string_formattext": "NEW Example"}' https://dnt.iondv.com/rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b
   # Или эквивалентно
   curl -X PUT -u demo@local:demo-ion -H "Content-Type:application/json" -d '{"string_text": "NEW Example", "string_miltilinetext": "NEW Example", "string_formattext": "NEW Example"}' https://dnt.iondv.com/rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b

Пример запроса к сервису crud для обновления объекта в :doc:`dnt </4_modules/modules/rest/services/services_files/request/request_examples>`:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /Checking crud service/PATCH/# updating an object (PATCH)

Если объект существует - возвращает код ответа ``200`` и сам объект в формате json, если объект не найден код ``404``\ , при ошибке обработки код ``500``\ , если нет прав ``403``.

Пример объекта.

.. code-block:: js

   {
       "_editor": "admin@local",
       "_id": "66dbb3d0-5583-11e6-aef7-cf50314f026b",
       "__string": "NEW Example",
       "__class": "class_string@develop-and-test",
       "__classTitle": "Class \"String [0]\"",
       "id": "66dbb3d0-5583-11e6-aef7-cf50314f026b",
       "string_text": "NEW Example",
       "string_miltilinetext": "NEW Example",
       "string_formattext": "NEW Example"
   }
