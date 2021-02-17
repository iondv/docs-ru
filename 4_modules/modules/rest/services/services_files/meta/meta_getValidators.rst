Получение списка доступных валидаторов ввода: getValidators
===========================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getValidators``, например:

.. code-block:: text

    https://localhost:8888/rest/meta/getValidators

будет запрошен список доступных валидаторов.

Этот пример в :doc:`dnt </4_modules/modules/rest/services/services_files/request/request_examples>`:
`test/modules/rest/metadatasrv.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/metadatasrv.spec.js>`_

.. code-block:: text

    /checking metadata service/# access information about input validators: getValidators
