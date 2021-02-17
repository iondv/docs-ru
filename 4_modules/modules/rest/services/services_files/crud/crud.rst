Встроенный сервис crud
======================

**Сервис crud** реализует REST API по модели основных операций CRUD (create, read, update, delete).

Доступен по адресу ``<адрес сервера>/rest/crud``.

Сервис требует регистрации в deploy.json приложения и обязательного указания источника данных ``dataRepo`` в ``options``
сервиса, а также источника авторизации ``auth`` для доступа к данным пользователя.
Целесообразно указывать в качестве репозитория данных - репозиторий с полной обработкой безопасности, чтобы отрабатывать
доступ к объектам с учетом динамической безопаности. Например:

.. code-block:: js

   {
     "modules": {
       "rest": {
         "globals": {
           "di": {
             "crud": {
               "module": "modules/rest/lib/impl/crud",
               "options": {
                 "auth": "ion://auth",
                 "dataRepo": "ion://securedDataRepo"
               }
             }

Аутентификация осуществляется через все основные :doc:`типы доступа </4_modules/modules/rest/authorization/authorization>`.

Пример:

.. code-block:: bash

   curl -X POST -u demo@local:ion-demo https://dnt.iondv.com/rest/crud

Пример запроса к сервису crud без параметров в :doc:`dnt </4_modules/modules/rest/services/services_files/request/request_examples>`:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/blob/master/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /Checking crud service/# check if the response for null parameters is valid

По умолчанию, без правильных параметров - код ответа сервера ``404`` об ошибке

.. code-block:: html

   <!DOCTYPE html>
   <html lang="en">
   <head>
   <meta charset="utf-8">
   <title>Error</title>
   </head>
   <body>
   <pre>Cannot POST /rest/crud</pre>
   </body>
   </html>

**Информация по взаимодействию с crud через основные методы:**

.. toctree::
   :titlesonly:
   
   crud_post
   crud_get
   crud_search
   crud_head
   crud_patch
   crud_delete
   ../request/request_with_files
