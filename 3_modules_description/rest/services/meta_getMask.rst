
Получение информации о маске формы представления: getMask
=========================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getMask/<имя маски>``. Например:

.. code-block:: text

    https://localhost:8888/rest/meta/getMask/snils

будет запрошен объект маски ``snils``.

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# access information about view mask: getMask