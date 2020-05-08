
Встроенный сервис "acceptor"
============================

Сервис ``acceptor`` предназначен для массового сохранения объектов разных классов.

Доступен по адресу ``<адрес сервера>/rest/acceptor``.

Для работы с сервисом требуется его регистрация в файле конфигураций приложений deploy.json. При этом для сервиса
обязательно должны быть указаны в ``options`` репозитории ``dataRepo`` и ``metaRepo``. Например

.. code-block:: js

   {
     "modules": {
       "rest": {
         "globals": {
           "di": {
             "acceptor": {
               "module": "modules/rest/lib/impl/acceptor",
               "options": {
                 "dataRepo": "ion://dataRepo",
                 "metaRepo": "ion://metaRepo"
               }
             }

Авторизация осуществляется через все основные :doc:`типы доступа <../authorization/index>`.

Сервис работает по методу ``POST``\ , объекты передаются в виде массива объектов в формате JSON в теле запроса с обязательным
указанием в заголовке содержания json ``Content-Type:application/json``. Автосоздаваемые поля указывать не обязательно.

В заголовке (header) в свойстве ``ion-converter`` может быть передано имя конвертора, который нужно использовать при обработке данных, как запроса, так и ответа.
При этом сам конвертор данных должен быть зарегистрирован в ``options`` сервиса.
Если обработчик не указан, используется обработчик по умолчанию.

В данных объекта обязательно указываются:


* ``_id`` - идентификатор объекта по ключевому полю
* ``_class`` - класс объекта с неймспейсом
* ``_classVer`` - версия класса

Остальные значения должны соответствовать свойствам класса, включая соответствие типов данных. Пример.

.. code-block:: bash

   curl -X POST -u demo@local:ion-demo \
      -H "Content-Type:application/json" \
      -d '[{"_class": "class_string@develop-and-test", "__classVer": null,"id": "10101010-5583-11e6-aef7-cf50314f026b",\
          "string_text": "Example10", "string_miltilinetext": "Example10", "string_formattext": "Example10"}]' \
      https://dnt.iondv.com/rest/acceptor

пример запроса на создание объектов к сервису acceptor в :doc:`dnt <request_examples>`:
`test/modules/rest/acceptor.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/acceptor.spec.js>`_

.. code-block:: text

    /Checking acceptor service/# basicAuth authorization with admin rights, POSTing strings/# result of creation of objects

Метод возвращает код ``200`` и массив сохраненных объектов.

.. code-block:: js

   [
     {
       "id": "10101010-5583-11e6-aef7-cf50314f026b",
       "_class": "class_string@develop-and-test",
       "_classVer": "",
       "string_formattext": "Example10",
       "string_miltilinetext": "Example10",
       "string_text": "Example10",
       "_id": "10101010-5583-11e6-aef7-cf50314f026b"
     }
   ]

В случае ошибки код ответа будет ``400``\ , а текст ответа содержать

.. code-block:: html

   <!DOCTYPE html>
   <html lang="en">
   <head>
   <meta charset="utf-8">
   <title>Error</title>
   </head>
   <body>
   <pre>Bad Request</pre>
   </body>
   </html>
