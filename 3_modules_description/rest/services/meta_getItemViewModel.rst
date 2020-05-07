
Получение информации о форме представления объектов класса при редактировании: getItemViewModel
===============================================================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getItemViewModel/<имя класса>``,
где имя класса указывается с неймспейсом. Например:

.. code-block:: text

    https://localhost:8888/rest/meta/getItemViewModel/class_text@develop-and-test

будет запрошен объект представления объектов класса ``class_text`` при их редактировании в неймспейсе ``develop-and-test``, пример ответа:

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
  type: 'item',
  className: 'class_text@develop-and-test',
  path: '' }
