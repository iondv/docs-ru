
Получение списка всех классов метаданных: listMeta
==================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/listMeta``.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``ancestor``
* ``version``
* ``direct``
* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/listMeta

будет запрошена информация по всем классам из метарепозитория, указанного в настройках сервиса ``meta`` в ``deploy.json``.

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /Checking metadata service/# accessing the list of metadata classes: listMeta