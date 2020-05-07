
Получение списка узлов навигации в секции: getNodes
===================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getNodes/<код секции>``,
где код секции указывается в формате ``namespace@name``. Например:

.. code-block:: text

    https://localhost:8888/rest/meta/getNodes/develop-and-test@simpleTypes

будет запрошен список узлов навигации в секции ``simpleTypes`` в неймспейсе ``develop-and-test``.
