Запросы к сервисам на примере тестов
====================================

Примеры запросов к основным сервисам REST можно найти в подготовленных для этих сервисов тестах.
Тесты написаны для `mocha <https://mochajs.org/>`_ и находятся в `репозитории приложения iondv develop-and-test <https://github.com/iondv/develop-and-test>`_.

Для запуска тестов нужно установить пакеты ``request-promise-native`` и ``mocha``,
например запустив ``npm install`` в папке ``develop-and-test/test``.

Предварительно нужно сконфигурировать параметры сервера и пользователей в ``develop-and-test/test/modules/rest/config.js``.

Запуск осуществляется вызовом ``mocha/lib/cli/cli.js`` для тестового скрипта, например:

.. code-block:: bash

    node node_modules/mocha/lib/cli/cli.js modules/rest/echo.spec.js

Можно запустить все тесты в папке:

.. code-block:: bash

    node node_modules/mocha/lib/cli/cli.js modules/rest/*.spec.js

Также возможен запуск отдельных юнит-тестов:

.. code-block:: bash

    node node_modules/mocha/lib/cli/cli.js -g "<ЧАСТЬ НАЗВАНИЯ ТЕСТА>" modules/rest/*.spec.js

например:

.. code-block:: bash

    node node_modules/mocha/lib/cli/cli.js -g "creating an object" modules/rest/*.spec.js
