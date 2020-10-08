Получение списка всех классов метаданных: listMeta
==================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/listMeta``.

В запросе можно указать `дополнительные параметры <meta_query_parameters.rst>`_:

* ``ancestor``
* ``version``
* ``direct``
* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/listMeta

будет запрошена информация по всем классам из метарепозитория, указанного в настройках сервиса ``meta`` в ``deploy.json``.

Этот пример в `dnt </4_modules/modules/rest/services/sevices_files/request/request_examples.rst>`_:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# accessing the list of metadata classes: listMeta
