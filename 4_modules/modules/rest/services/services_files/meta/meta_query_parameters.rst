Дополнительные параметры запросов к сервису метаданных
======================================================

В большинстве запросов к сервису метаданных (``meta``), помимо самого запроса, можно указать
дополнительные параметры. Список дополнительных параметров, которые необходимо применить к запросу
начинается символом ``?``, после этого пишется название и значение параметра через знак ``=``,
несколько параметров разделяются между собой с помощью ``&``.

Пример GET запроса к ``meta/getList`` с дополнительным параметром ``ancestor`` - фильтрацией по предку:

.. code-block:: text

    https://localhost:8888/rest/meta/listMeta?ancestor=basicObj@develop-and-test

В ответ будет возвращен список классов метаданных, которые являются производными от ``basicObj``.

Этот пример в :doc:`dnt </4_modules/modules/rest/services/services_files/request/request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/blob/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# accessing the list of metadata classes filtering by ancestor: listMeta
