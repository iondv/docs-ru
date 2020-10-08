Получение информации о бизнес-процессе класса: getWorkflow
==========================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getWorkflow/<имя класса>/<имя бизнес-процесса>``,
где имя класса и имя бизнес-процесса указываются с неймспейсом.

В запросе можно указать `дополнительные параметры <meta_query_parameters.rst>`_:

* ``workflow``
* ``namespace``
* ``version``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getWorkflow/workflowBase@develop-and-test/simpleWorkflow@develop-and-test

будет запрошен объект бизнес-процесса ``simpleWorkflow`` для класса объектов ``workflowBase`` в неймспейсе ``develop-and-test``. Пример ответа:

.. code-block:: js

    { name: 'simpleWorkflow',
  caption: 'Simple WF',
  wfClass: 'workflowBase@develop-and-test',
  startState: 'canStart',
  states:
   [ { name: 'canStart',
       caption: 'Ready to check',
       maxPeriod: null,
       conditions: [Object],
       propertyPermissions: [],
       itemPermissions: [],
       selectionProviders: [] },
     { name: 'inProcess',
       caption: 'In process',
       maxPeriod: null,
       conditions: null,
       itemPermissions: [Array],
       propertyPermissions: [],
       selectionProviders: [] },
     { name: 'accepted',
       caption: 'Accepted',
       maxPeriod: null,
       conditions: null,
       itemPermissions: [],
       propertyPermissions: [],
       selectionProviders: [] },
     { name: 'returned',
       caption: 'Returned',
       maxPeriod: null,
       conditions: null,
       itemPermissions: [Array],
       propertyPermissions: [],
       selectionProviders: [] },
     { name: 'rejected',
       caption: 'Rejected',
       maxPeriod: null,
       conditions: null,
       itemPermissions: [],
       propertyPermissions: [],
       selectionProviders: [] } ],
  transitions:
   [ { name: 'startCheck',
       caption: 'Start checking',
       startState: 'canStart',
       finishState: 'inProcess',
       signBefore: false,
       signAfter: false,
       roles: [],
       assignments: [Array],
       conditions: null,
       confirm: false,
       confirmMessage: null },
     { name: 'return',
       caption: 'Return',
       startState: 'inProcess',
       finishState: 'returned',
       signBefore: false,
       signAfter: false,
       roles: [],
       assignments: [Array],
       conditions: null,
       confirm: false,
       confirmMessage: null },
     { name: 'accept',
       caption: 'Accept',
       startState: 'inProcess',
       finishState: 'accepted',
       signBefore: false,
       signAfter: false,
       roles: [],
       assignments: [Array],
       conditions: null,
       confirm: false,
       confirmMessage: null },
     { name: 'reject',
       caption: 'Reject',
       startState: 'inProcess',
       finishState: 'rejected',
       signBefore: false,
       signAfter: false,
       roles: [],
       assignments: [Array],
       conditions: null,
       confirm: false,
       confirmMessage: null },
     { name: 'notify',
       caption: 'To check',
       startState: 'returned',
       finishState: 'canStart',
       signBefore: false,
       signAfter: false,
       roles: [],
       assignments: [Array],
       conditions: [Object],
       confirm: false,
       confirmMessage: null } ],
  metaVersion: '2.0.61.16945',
  namespace: 'develop-and-test' }

Этот пример в `dnt </4_modules/modules/rest/services/sevices_files/request/request_examples.rst>`_:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# access information about workflow: getWorkflow
