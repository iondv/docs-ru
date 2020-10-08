Получение списка секций навигации: getNavigationSections
========================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getNavigationSections``.

В запросе можно указать `дополнительные параметры <meta_query_parameters.rts>`_:

* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getNavigationSections

будет запрошен список всех объектов секций навигации из метарепозитория, указанного в настройках сервиса ``meta`` в ``deploy.json``.

Этот пример в `dnt </4_modules/modules/rest/services/sevices_files/request/request_examples.rst>`_:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# accessing the list of navigation sections: getNavigationSections
