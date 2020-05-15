
Получение информации о секции навигации: getNavigationSection
=============================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getNavigationSection/<код секции>``,
где код секции указывается в формате ``namespace@name``.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getNavigationSection/develop-and-test@simpleTypes

будет запрошен объект секции навигации ``simpleTypes`` в неймспейсе ``develop-and-test``, пример ответа:

.. code-block:: js

    { caption: 'Simple types',
        code: 'simpTypes',
        name: 'simpleTypes',
        orderNumber: 20,
        mode: 0,
        tags: null,
        metaVersion: '2.0.7',
        itemType: 'section',
        namespace: 'develop-and-test',
        nodes:
        { class_boolean:
          { namespace: 'develop-and-test',
            code: 'class_boolean',
            orderNumber: 0,
            type: 0,
            caption: 'Class "Boolean [10]"',
            classname: null,
            container: null,
            collection: null,
            url: null,
            hint: null,
            conditions: null,
            sorting: [],
            pathChains: [],
            title: '',
            metaVersion: '2.0.0',
            itemType: 'node',
            section: 'develop-and-test@simpleTypes',
            children: [Array] },
         class_custom:
          { namespace: 'develop-and-test',
            code: 'class_custom',
            orderNumber: 0,
            type: 1,
            caption: 'Class "User type [17]"',
            classname: 'class_custom@develop-and-test',
            container: null,
            collection: null,
            url: null,
            hint: null,
            conditions: null,
            sorting: [],
            pathChains: [],
            title: '',
            metaVersion: '2.0.0',
            itemType: 'node',
            section: 'develop-and-test@simpleTypes',
            children: [] },
         class_datetime:
          { namespace: 'develop-and-test',
            code: 'class_datetime',
            orderNumber: 0,
            type: 1,
            caption: 'Class "Date/time [9]"',
            classname: 'class_datetime@develop-and-test',
            container: null,
            collection: null,
            url: null,
            hint: null,
            conditions: null,
            sorting: [],
            pathChains: [],
            title: '',
            metaVersion: '2.0.0',
            itemType: 'node',
            section: 'develop-and-test@simpleTypes',
            children: [] },
         class_decimal:
          { code: 'class_decimal',
            orderNumber: 0,
            type: 1,
            caption: 'Class "Decimal [8]"',
            classname: 'class_decimal@develop-and-test',
            container: null,
            collection: null,
            url: null,
            hint: null,
            conditions: null,
            sorting: [],
            pathChains: [],
            metaVersion: '2.0.7',
            itemType: 'node',
            section: 'develop-and-test@simpleTypes',
            namespace: 'develop-and-test',
            children: [] }
        }
    }

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# access info about a navigation section: getNavigationSection