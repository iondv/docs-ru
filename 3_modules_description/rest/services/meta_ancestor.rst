
Получение информации о классе-предке: ancestor
==============================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/ancestor/<имя класса>``,
где имя класса указывается с неймспейсом.

В запросе можно указать :doc:`дополнительные параметры <meta_query_parameters>`:

* ``version``
* ``namespace``

Пример запроса:

.. code-block:: text

    https://localhost:8888/rest/meta/getMeta/event@develop-and-test

будет запрошена информация по классу-предку класса ``event`` в неймспейсе ``develop-and-test`` - ``basicObj``.

Этот пример в :doc:`dnt <request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# accessing info about class ancestor
