Получение информации о форме представления объекта класса при некотором состоянии бизнес-процесса: getListViewModel
===================================================================================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getListViewModel/<имя класса>/<имя бизнес-процесса>/<имя состояния>``,
где имя класса и имя бизнес-процесса указываются с неймспейсом.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``workflow``
* ``state``
* ``namespace``
* ``version``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getWorkflowView/workflowBase@develop-and-test/simpleWorkflow@develop-and-test/canStart

будет запрошен объект представления объектов класса ``workflowBase`` при состоянии ``canStart`` бизнес-процесса ``simpleWorkflow`` в неймспейсе ``develop-and-test``, пример ответа:

.. code-block:: js

    { tabs: [ { caption: '', fullFields: [Array], shortFields: [] } ],
  actions: null,
  siblingFixBy: null,
  siblingNavigateBy: null,
  historyDisplayMode: 0,
  collectionFilters: null,
  version: null,
  overrideMode: 1,
  commands:
   [ { id: 'SAVE',
       caption: 'Save',
       visibilityCondition: null,
       enableCondition: null,
       needSelectedItem: false,
       signBefore: false,
       signAfter: false,
       isBulk: false },
     { id: 'SAVEANDCLOSE',
       caption: 'Save and close',
       visibilityCondition: null,
       enableCondition: null,
       needSelectedItem: false,
       signBefore: false,
       signAfter: false,
       isBulk: false } ],
  metaVersion: '2.0.61',
  type: 'item',
  className: 'workflowBase@develop-and-test',
  path: 'workflows:simpleWorkflow@develop-and-test.canStart',
  caption: '' }

Этот пример в :doc:`dnt </4_modules/modules/rest/services/services_files/request/request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# access meta class view model in a certain workflow state: getWorkflowView
