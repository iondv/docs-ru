
Проверка наличия объекта: метод HEAD
====================================

Проверка наличия объекта осуществляется методом ``HEAD``\ , при этом указывается код класса с нейспейсом и значение ключа объекта,
например ``rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b``

.. code-block:: bash

   curl -X HEAD -u demo@local:ion-demo https://dnt.iondv.com/rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b

пример запроса к сервису crud для проверки наличия объекта в :doc:`dnt <request_examples>`:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /Checking crud service/HEAD/# checking if an object is present (HEAD)

Если объект существует - возвращает код ответа ``200``\ , если объект не найден ``404``\ , если нет прав ``403``.
