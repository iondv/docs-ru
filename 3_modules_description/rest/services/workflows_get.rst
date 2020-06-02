
Получение текущего положения обьекта в бизнес-процессе: GET
===========================================================

Методом GET осуществляется получение текущего положения обьекта в бизнес-процессах.
Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/<имя класса>/<id объекта>``, пример:

.. code-block:: text

    https://localhost:8888/rest/workflows/workflowBase@develop-and-test/1

В ответ будет получен объект с состояниями бизнес-процессов:

.. code-block:: js

    { stages:
        { 'simpleWorkflow@develop-and-test':
          { stage: 'inProcess',
            since: '2020-05-12T06:36:06.045Z',
            next: [Object],
            workflowCaption: 'Simple WF',
            stageCaption: 'In process' } },
        itemPermissions: { read: true },
        propertyPermissions: {},
        selectionProviders: {} }

Пример ``GET`` запроса к ``workflows`` в :doc:`dnt <request_examples>`:
`test/modules/rest/workflows.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/workflows.spec.js>`_

.. code-block:: text

    /checking workflows service/# accessing workflow statuses of the object: GET
