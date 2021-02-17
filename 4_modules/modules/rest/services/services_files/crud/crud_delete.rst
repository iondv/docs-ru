Удаление объекта: метод DELETE
==============================

**Удаление объекта** осуществляется методом ``DELETE``\ , при этом указывается код класса с нейспейсом и значение ключа объекта,
например ``rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b``.

.. code-block:: bash

   curl -X DELETE -u demo@local:demo-ion https://dnt.iondv.com/rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b

Пример запроса к сервису crud на удаление объектов в :doc:`dnt </4_modules/modules/rest/services/services_files/request/request_examples>`: `test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /Checking crud service/DELETE/# deleting an object (DELETE)

В случае успеха - сервис возвращает код ответа ``200``\ , в случае если объект не найден ``404``.
