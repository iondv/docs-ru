Получение информации об узле навигации: getNode
=================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getNode/<код навигации>``,
где код навигации указывается в формате ``namespace@code``.

В запросе можно указать `дополнительные параметры <meta_query_parameters.rst>`_:

* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getNode/develop-and-test@semantic

будет запрошен объект узла навигации ``semantic`` в неймспейсе ``develop-and-test``, пример ответа:

.. code-block:: js

    { code: 'semantic',
    orderNumber: 0,
    type: 0,
    caption: 'Display semantics [semantic]',
    classname: null,
    container: null,
    collection: null,
    url: null,
    hint: null,
    conditions: null,
    sorting: [],
    pathChains: [],
    metaVersion: '2.0.61',
    itemType: 'node',
    section: 'develop-and-test@classProperties',
    namespace: 'develop-and-test',
    children:
    [ { code: 'semantic.semErrCatalog',
       orderNumber: 0,
       type: 1,
       caption:
        'Catalog for checking semantics (string1| |string2| |string3| |date| |integer)',
       classname: 'semErrCatalog@develop-and-test',
       container: null,
       collection: null,
       url: null,
       hint: null,
       conditions: null,
       sorting: [],
       pathChains: [],
       metaVersion: '2.0.61',
       itemType: 'node',
       section: 'develop-and-test@classProperties',
       namespace: 'develop-and-test',
       children: [] },
     { code: 'semantic.semErrClass',
       orderNumber: 0,
       type: 1,
       caption: 'Attribute semantics is taken from reference class',
       classname: 'semErrClass@develop-and-test',
       container: null,
       collection: null,
       url: null,
       hint: null,
       conditions: null,
       sorting: [],
       pathChains: [],
       metaVersion: '2.0.61',
       itemType: 'node',
       section: 'develop-and-test@classProperties',
       namespace: 'develop-and-test',
       children: [] }]
    }

Этот пример в `dnt </4_modules/modules/rest/services/sevices_files/request/request_examples.rst>`_:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# access info about a navigation node: getNode
