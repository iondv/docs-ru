Получение информации о свойствах объектов класса: propertyMetas
===============================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/propertyMetas/<имя класса>``,
где имя класса указывается с неймспейсом.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``version``
* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/propertyMetas/class_text@develop-and-test

будет запрошена информация о свойствах объектов класса ``class_text`` в неймспейсе ``develop-and-test``, например:

.. code-block:: js

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
    formula: null,
    definitionClass: 'class_text@develop-and-test',
    mode: 0 },
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
    formula: null,
    definitionClass: 'class_text@develop-and-test',
    mode: 0 },
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
    formula: null,
    definitionClass: 'class_text@develop-and-test',
    mode: 0 },
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
    formula: null,
    definitionClass: 'class_text@develop-and-test',
    mode: 0 } ]

Этот пример в :doc:`dnt </4_modules/modules/rest/services/services_files/request/request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# accessing info about meta object properties: propertyMetas
