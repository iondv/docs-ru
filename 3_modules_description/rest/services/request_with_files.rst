
Отправка запросов с файлами в CRUD сервисе
==========================================

При запросе к CRUD методами **POST**, **PATCH** и **PUT**, в теле запроса можно передать файлы.

Отправка и прием файлов осуществляется двумя способами:

* данные отправляются в формате ``json``, тогда контент файла передается как строка в формате *Base64* в соответствующем поле класса метаданных.
* данные отправляются как ``FormData`` (application/x-www-form-urlencoded), тогда файлы передаются как компонент *multipart*.

Корректный прием файловых атрибутов в случае отправки таких запросов осуществляется методами ``POST``, ``PUT`` и ``PATCH`` в CRUD сервисе.

Так же возможна передача ссылок и коллекций по примеру, описанному для `soap модуля <https://github.com/iondv/soap>`_.

Примеры **POST** запросов с файлами к ``CRUD`` в :doc:`dnt <request_examples>`:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /checking crud service/# sending a file with multipart body request (POST)
    /checking crud service/# sending a file with json body request (POST)
