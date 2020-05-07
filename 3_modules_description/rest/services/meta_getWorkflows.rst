
Получение списка возможных бизнес-процессов для класса: getWorkflows
====================================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getWorkflows/<имя класса>``,
где имя класса указывается с неймспейсом. Например:

.. code-block:: text

    https://localhost:8888/rest/meta/getMeta/workflowBase@develop-and-test

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