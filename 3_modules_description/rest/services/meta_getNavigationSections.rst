
Получение списка секций навигации: getNavigationSections
========================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getNavigationSections``.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getNavigationSections

будет запрошен список всех объектов секций навигации из метарепозитория, указанного в настройках сервиса ``meta`` в ``deploy.json``.

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /Checking metadata service/# accessing the list of navigation sections: getNavigationSections