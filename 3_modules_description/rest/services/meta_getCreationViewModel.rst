
Получение информации о форме представления объектов класса при создании: getCreationViewModel
=============================================================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getCreationViewModel/<имя класса>``,
где имя класса указывается с неймспейсом.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``node``
* ``namespace``
* ``version``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getCreationViewModel/class_text@develop-and-test

будет запрошен объект представления объектов класса ``class_text`` при их создании в неймспейсе ``develop-and-test``, пример ответа:

.. code-block:: js

    { tabs: [ { caption: '', fullFields: [Array], shortFields: [] } ],
  actions: null,
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
  siblingFixBy: null,
  siblingNavigateBy: null,
  historyDisplayMode: 0,
  collectionFilters: null,
  version: null,
  overrideMode: null,
  metaVersion: '2.0.7',
  type: 'create',
  className: 'class_text@develop-and-test',
  path: '',
  caption: '' }

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /Checking metadata service/# access meta class creation view model: getCreationViewModel