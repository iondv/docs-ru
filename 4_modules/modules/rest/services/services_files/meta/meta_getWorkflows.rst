Получение списка возможных бизнес-процессов для класса: getWorkflows
====================================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getWorkflows/<имя класса>``,
где имя класса указывается с неймспейсом.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``namespace``
* ``version``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getWorkflows/workflowBase@develop-and-test

будет запрошен список бизнес-процессов для класса ``workflowBase`` в неймспейсе ``develop-and-test``, пример ответа:

.. code-block:: js

    [ { name: 'simpleWorkflow',
    caption: 'Simple WF',
    wfClass: 'workflowBase@develop-and-test',
    startState: 'canStart',
    states: [ [Object], [Object], [Object], [Object], [Object] ],
    transitions: [ [Object], [Object], [Object], [Object], [Object] ],
    metaVersion: '2.0.61.16945',
    namespace: 'develop-and-test' } ]

Этот пример в :doc:`dnt </4_modules/modules/rest/services/services_files/request/request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# accessing the list of possible workflows for meta class: getWorkflows
