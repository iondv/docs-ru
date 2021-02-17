Сервисы REST
============

.. toctree::
   :hidden:
   :titlesonly:
   
   services_files/acceptor
   services_files/token
   services_files/crud/crud
   services_files/meta/metadata_service
   services_files/workflow/workflows_service
   services_files/custom_service
   services_files/service_configuration
   services_files/request/request_examples

Модуль REST имеет несколько встроенных сервисов, предназначенных для реализации типовых операций с модулем:

* :doc:`Сервис Acceptor <services_files/acceptor>`  -  обеспечивает массовое создание объектов.
* :doc:`Сервис Token <services_files/token>` - обеспечивает выдачу токена для авторизованного пользователя.
* :doc:`Сервис CRUD <services_files/crud/crud>` - сервис CRUD для объектов системы.
* :doc:`Cервис Meta <services_files/meta/metadata_service>` - обеспечивает доступ к интерфейсу метаданных.
* :doc:`Cервис Workflows <services_files/workflow/workflows_service>` - обеспечивает возможности контролировать и управлять бизнес-процессами.

Также поддерживается разработка и подключение пользовательских сервисов.

Разработка обработчика в приложении - :doc:`подробнее <services_files/custom_service>`.

Регистрация сервиса в конфигурации приложения - :doc:`подробнее <services_files/service_configuration>`.
