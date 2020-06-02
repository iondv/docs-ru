
Получение информации о списочной форме представления объектов класса: getListViewModel
======================================================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getListViewModel/<имя класса>``,
где имя класса указывается с неймспейсом.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``node``
* ``namespace``
* ``version``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getListViewModel/class_text@develop-and-test

будет запрошен объект представления объектов класса ``class_text`` в списочной форме в неймспейсе ``develop-and-test``, пример ответа:

.. code-block:: js

    { columns:
   [ { sorted: true,
       caption: 'Identifier',
       type: 1,
       property: 'id',
       size: 2,
       maskName: null,
       mask: null,
       mode: null,
       fields: [],
       hierarchyAttributes: null,
       columns: [],
       actions: null,
       commands: [],
       orderNumber: 10,
       required: false,
       visibility: null,
       enablement: null,
       obligation: null,
       readonly: true,
       selectionPaginated: true,
       validators: null,
       hint: '',
       historyDisplayMode: 0,
       tags: null },
     { sorted: true,
       caption: 'Text [1]',
       type: 1,
       property: 'text_text',
       size: 2,
       maskName: null,
       mask: null,
       mode: null,
       fields: [],
       hierarchyAttributes: null,
       columns: [],
       actions: null,
       commands: [],
       orderNumber: 20,
       required: false,
       visibility: null,
       enablement: null,
       obligation: null,
       readonly: false,
       selectionPaginated: true,
       validators: null,
       hint: '',
       historyDisplayMode: 0,
       tags: null },
     { sorted: true,
       caption: 'Multiline text [7]',
       type: 7,
       property: 'text_multilinetext',
       size: 2,
       maskName: null,
       mask: null,
       mode: null,
       fields: [],
       hierarchyAttributes: null,
       columns: [],
       actions: null,
       commands: [],
       orderNumber: 30,
       required: false,
       visibility: null,
       enablement: null,
       obligation: null,
       readonly: false,
       selectionPaginated: true,
       validators: null,
       hint: '',
       historyDisplayMode: 0,
       tags: null },
     { sorted: true,
       caption: 'Formatted text [8]',
       type: 8,
       property: 'text_formattext',
       size: 2,
       maskName: null,
       mask: null,
       mode: null,
       fields: [],
       hierarchyAttributes: null,
       columns: [],
       actions: null,
       commands: [],
       orderNumber: 40,
       required: false,
       visibility: null,
       enablement: null,
       obligation: null,
       readonly: false,
       selectionPaginated: true,
       validators: null,
       hint: '',
       historyDisplayMode: 0,
       tags: null } ],
  actions: null,
  commands:
   [ { id: 'CREATE',
       caption: 'Create',
       visibilityCondition: null,
       enableCondition: null,
       needSelectedItem: false,
       signBefore: false,
       signAfter: false,
       isBulk: false },
     { id: 'EDIT',
       caption: 'Edit',
       visibilityCondition: null,
       enableCondition: null,
       needSelectedItem: true,
       signBefore: false,
       signAfter: false,
       isBulk: false },
     { id: 'DELETE',
       caption: 'Delete',
       visibilityCondition: null,
       enableCondition: null,
       needSelectedItem: false,
       signBefore: false,
       signAfter: false,
       isBulk: true } ],
  allowSearch: false,
  pageSize: null,
  useEditModels: true,
  version: null,
  overrideMode: null,
  metaVersion: '2.0.7',
  type: 'list',
  className: 'class_text@develop-and-test',
  path: '',
  caption: '' }

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# access meta class list view model: getListViewModel
