Встроенный сервис crud
========================

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

Аутентификация осуществляется через все основные `типы доступа </4_modules/modules/rest/authorization/authorization.rst>`.

Пример:

.. code-block:: bash

   curl -X POST -u demo@local:ion-demo https://dnt.iondv.com/rest/crud

Пример запроса к сервису crud без параметров в `dnt </4_modules/modules/rest/services/sevices_files/request/request_examples.rst>`_:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/blob/master/test/modules/rest/crud.spec.js>`_

.. code-block:: test

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

* Создание объекта: `метод POST <crud_post.rst>`_
* Получение объекта или списка объектов: `метод GET <crud_get.rst>`_
* Получение объектов `методом SEARCH <crud_search.rst>`_
* Проверка наличия объекта: `метод HEAD <crud_head.rst>`_
* Обновление объекта: `методы PATCH и PUT <crud_patch.rst>`_
* Удаление объекта: `метод DELETE <crud_delete.rst>`_
* Отправка `запросов с файлами </4_modules/modules/rest/services/sevices_files/request/request_with_files.rst>`_
