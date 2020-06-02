
Создание объекта: метод POST
============================

Создание объекта осуществляется методом ``POST``\ , при этом указывается код класса с нейспейсом,
например ``rest/crud/class_string@develop-and-test``. Сам объект передается в теле запроса в формате json с обязательным
указанием в заголовке типа содержания json ``Content-Type:application/json``. Автосоздаваемые поля указывать не обязательно.

Пример:

.. code-block:: bash

   curl -X POST -u demo@local:ion-demo \
      -H "Content-Type:application/json" \
      -d '{"string_text": "Example3", "string_miltilinetext": "Example3", "string_formattext": "Example3"}' \
      https://dnt.iondv.com/rest/crud/class_string@develop-and-test/

пример запроса к сервису crud для создания объекта :doc:`dnt <request_examples>`:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /Checking crud service/POST/# creating an object (POST)

В ответ будет возвращён созданный объект, в котором будут заполнены все автосозданные поля и указан код ответа ``200``.

.. code-block:: js

   {
       "_creator": "admin@local",
       "_id": "10c77900-b96e-11e9-a7ce-314f02bd4197",
       "__string": "10c77900-b96e-11e9-a7ce-314f02bd4197",
       "__class": "class_string@develop-and-test",
       "__classTitle": "Class \"String [0]\"",
       "id": "10c77900-b96e-11e9-a7ce-314f02bd4197",
       "string_text": "Example3",
       "string_miltilinetext": "Example3",
       "string_formattext": "Example3"
   }

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
