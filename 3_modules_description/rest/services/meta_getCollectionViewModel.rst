
Получение информации о форме представления объектов класса в виде коллекции: getCollectionViewModel
===================================================================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getCollectionViewModel/<имя класса>``,
где имя класса указывается с неймспейсом.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``collection``
* ``node``
* ``namespace``
* ``version``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getCollectionViewModel/class_text@develop-and-test

будет запрошен объект представления объектов класса ``class_text`` в форме коллекции в неймспейсе ``develop-and-test``.

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /Checking metadata service/# access meta class collection view model: getCollectionViewModel