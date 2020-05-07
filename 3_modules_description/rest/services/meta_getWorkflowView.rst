
Получение информации о форме представления объекта класса при некотором состоянии бизнес-процесса: getListViewModel
===================================================================================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getListViewModel/<имя класса>/<имя бизнес-процесса>/<имя состояния>``,
где имя класса и имя бизнес-процесса указываются с неймспейсом. Например:

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
