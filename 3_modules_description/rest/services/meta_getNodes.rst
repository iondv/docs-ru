
Получение списка узлов навигации в секции: getNodes
===================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getNodes/<код секции>``,
где код секции указывается в формате ``namespace@name``.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``section``
* ``parent``
* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getNodes/develop-and-test@simpleTypes

будет запрошен список узлов навигации в секции ``simpleTypes`` в неймспейсе ``develop-and-test``.

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# access the list of navigation nodes in a section: getNodes
