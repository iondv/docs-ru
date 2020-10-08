Получение информации о форме представления объектов класса в виде коллекции: getCollectionViewModel
===================================================================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getCollectionViewModel/<имя класса>``,
где имя класса указывается с неймспейсом.

В запросе можно указать `дополнительные параметры <meta_query_parameters.rst>`_:

* ``collection``
* ``node``
* ``namespace``
* ``version``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getCollectionViewModel/class_text@develop-and-test

будет запрошен объект представления объектов класса ``class_text`` в форме коллекции в неймспейсе ``develop-and-test``.

Этот пример в `dnt </4_modules/modules/rest/services/sevices_files/request/request_examples.rst>`_:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# access meta class collection view model: getCollectionViewModel
