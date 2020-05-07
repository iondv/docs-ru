
Получение списка секций навигации: getNavigationSections
========================================================

Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/getNavigationSections``, Например:

.. code-block:: text

    https://localhost:8888/rest/meta/getNavigationSections

будет запрошен список всех объектов секций навигации из метарепозитория, указанного в настройках сервиса ``meta`` в ``deploy.json``.