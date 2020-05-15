
Получение информации о классе метаданных: getMeta
=================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getMeta/<имя класса>``,
где имя класса указывается с неймспейсом.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``version``
* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getMeta/class_text@develop-and-test

будет запрошена информация по классу ``class_text`` в неймспейсе ``develop-and-test``, пример ответа:

.. code-block:: js

    { namespace: 'develop-and-test',
    isStruct: false,
    metaVersion: '2.0.7',
    key: [ 'id' ],
    semantic: '',
    name: 'class_text',
    version: '',
    caption: 'Class "Text [1]"',
    ancestor: null,
    container: null,
    creationTracker: '',
    changeTracker: '',
    history: 0,
    journaling: false,
    compositeIndexes: null,
    properties:
    [ { orderNumber: 10,
       name: 'id',
       caption: 'Identifier',
       type: 12,
       size: 24,
       decimals: 0,
       allowedFileTypes: null,
       maxFileCount: 0,
       nullable: false,
       readonly: false,
       indexed: true,
       unique: true,
       autoassigned: true,
       hint: null,
       defaultValue: null,
       refClass: '',
       itemsClass: '',
       backRef: '',
       backColl: '',
       binding: '',
       semantic: null,
       selConditions: null,
       selSorting: [],
       selectionProvider: null,
       indexSearch: false,
       eagerLoading: false,
       formula: null },
     { orderNumber: 20,
       name: 'text_text',
       caption: 'Text [1]',
       type: 1,
       size: null,
       decimals: 0,
       allowedFileTypes: null,
       maxFileCount: 0,
       nullable: true,
       readonly: false,
       indexed: true,
       unique: false,
       autoassigned: false,
       hint: null,
       defaultValue: null,
       refClass: '',
       itemsClass: '',
       backRef: '',
       backColl: '',
       binding: '',
       semantic: null,
       selConditions: null,
       selSorting: [],
       selectionProvider: null,
       indexSearch: false,
       eagerLoading: false,
       formula: null },
     { orderNumber: 30,
       name: 'text_multilinetext',
       caption: 'Multiline text [7]',
       type: 1,
       size: null,
       decimals: 0,
       allowedFileTypes: null,
       maxFileCount: 0,
       nullable: true,
       readonly: false,
       indexed: true,
       unique: false,
       autoassigned: false,
       hint: null,
       defaultValue: null,
       refClass: '',
       itemsClass: '',
       backRef: '',
       backColl: '',
       binding: '',
       semantic: null,
       selConditions: null,
       selSorting: [],
       selectionProvider: null,
       indexSearch: false,
       eagerLoading: false,
       formula: null },
     { orderNumber: 40,
       name: 'text_formattext',
       caption: 'Formatted text [8]',
       type: 1,
       size: null,
       decimals: 0,
       allowedFileTypes: null,
       maxFileCount: 0,
       nullable: true,
       readonly: false,
       indexed: true,
       unique: false,
       autoassigned: false,
       hint: null,
       defaultValue: null,
       refClass: '',
       itemsClass: '',
       backRef: '',
       backColl: '',
       binding: '',
       semantic: null,
       selConditions: null,
       selSorting: [],
       selectionProvider: null,
       indexSearch: false,
       eagerLoading: false,
       formula: null } ] }

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# accessing info about metadata class: getMeta