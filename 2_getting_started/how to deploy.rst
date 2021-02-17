Как развернуть
===============

.. toctree::
   :titlesonly:
   :hidden:

   how_to_deploy/1_install_environment
   how_to_deploy/2_core_modules_app
   how_to_deploy/3_build_and_run
   how_to_deploy/files_in_bin_folder

В данном разделе - о том, как развернуть систему.
Для развертывания системы необходимо выполнить несколько шагов.

Шаги
----

1. :doc:`Установка окружения <how_to_deploy/1_install_environment>`
2. :doc:`Установка ядра, модулей и приложения <how_to_deploy/2_core_modules_app>`
3. :doc:`Сборка и запуск приложения <how_to_deploy/3_build_and_run>`

Файлы в папке "bin"
-------------------

В папке "bin" содержатся скрипты запуска приложения, реализованного на IONDV. Framework, такие как:


* acl.js
* export.js
* import.js и import-data.js
* setup.js

.. code-block:: text

   NB. Запускаются локально из папки framework, шаблоны команд указаны в разделах с описанием назначения скрипта.
   

Подробнее о :doc:`файлах в папке "bin" <how_to_deploy/files_in_bin_folder>`.
