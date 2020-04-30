
Получение объекта или списка объектов: метод GET
================================================

Получение объекта
-----------------

Получение объекта осуществляется методом ``GET``\ , при этом указывается код класса с нейспейсом и значение ключа объекта,
например ``rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b``

.. code-block:: bash

   curl -X GET -u demo@local:ion-demo https://dnt.iondv.com/rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b

пример запроса к сервису crud для получения объекта в :doc:`dnt <request_examples>`:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /Checking crud service/GET/# getting an object (GET)

При этом дополнительно в query может быть задан параметр ``_eager`` содержащий список свойств класса, разделенных символом ``|``
для которых необходимо осуществить жадную загрузку данных (ссылки или коллекции). Например

.. code-block:: bash

   curl -X GET -u demo@local:ion-demo https://dnt.iondv.com/rest/crud/class_string@develop-and-test/66dbb3d0-5583-11e6-aef7-cf50314f026b?_eager=string_text

пример запроса к сервису crud для получения объекта с жадной загрузкой свойства "table" в :doc:`dnt <request_examples>`:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /Checking crud service/GET/# getting an object with eager loading of the "table" property (GET)

Если объект существует - возвращает код ответа ``200`` и сам объект в формате json, если объект не найден ``404``\ , если нет прав ``403``.

.. code-block:: js

   {
       "_id": "66dbb3d0-5583-11e6-aef7-cf50314f026b",
       "__string": "Example of the \"String [0]\" type in the \"Text [1]\" view",
       "__class": "class_string@develop-and-test",
       "__classTitle": "Class \"String [0]\"",
       "id": "66dbb3d0-5583-11e6-aef7-cf50314f026b",
       "string_text": "Example of the \"String [0]\" type in the \"Text [1]\" view",
       "string_miltilinetext": "Example of the \"String [0]\"\r\n in the Multiline text [7] view",
       "string_formattext": "Example of the \r\n \"String [0]\" type \r\n in the \r\nFormatted text [7] view"
   }

Получение списка объектов
-------------------------

Запрос списка объектов осуществляется методом ``GET``\ , при этом указывается код класса и нейспейс, например ``rest/crud/class_string@develop-and-test/``

.. code-block:: bash

   curl -X GET -u demo@local:ion-demo https://dnt.iondv.com/rest/crud/class_string@develop-and-test/

пример запроса к сервису crud для получения списка объектов в :doc:`dnt <request_examples>`:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /Checking crud service/GET/# getting a list of text objects

В ответ сервис выдает JSON Объект со смещением 0 и кол-вом 5ть записей и статусом ``200``\ , если такого класса нет возвращает код ``404``.

.. code-block:: js

   [{"_creator":"admin@local",
   "_id":"4567a830-b8ea-11e9-9cdf-7bd384cbb7a5",
   "__string":"example1",
   "__class":"class_string@develop-and-test",
   "__classTitle":"Class \"String [0]\"",
   "id":"4567a830-b8ea-11e9-9cdf-7bd384cbb7a5",
   "string_text":"example1",
   "string_miltilinetext":"example1",
   "string_formattext":"<p>example1</p>"},
   {"_id":"66dbb3d0-5583-11e6-aef7-cf50314f026b",
   "__string":"Example of the \"String [0]\" type in the \"Text [1]\" view",
   "__class":"class_string@develop-and-test",
   "__classTitle":"Class \"String [0]\"",
   "id":"66dbb3d0-5583-11e6-aef7-cf50314f026b",
   "string_text":"Example of the \"String [0]\" type in the \"Text [1]\" view",
   "string_miltilinetext":"Example of the \"String [0]\"\r\n in the Multiline text [7] view",
   "string_formattext":"Example of the \r\n \"String [0]\" type \r\n in the \r\nFormatted text [7] view"}]

Запрос может быть осуществлен со следущими query параметрами:


* ``_offset`` - смещение выборки, по умолчанию 0
* ``_count`` - кол-во значение в выборке, по умолчанию 5
* ``_eager`` - список свойств класса, разделенных символом ``|`` для которых необходимо осуществить жадную загрузку данных.
* ``[name of property]`` - все параметры воспринимаютсяимя запроса, кроме начинающихся на ``_`` считаются именами атрибутов класса,
  а их значения задаются в качестве фильтров.

Примеры:

#. Запрос списка объектов класса со смещением 1 и кол-вом 2

    .. code-block:: bash

        curl -X GET -u demo@local:ion-demo https://dnt.iondv.com/rest/crud/class_string@develop-and-test/?_offset=1&_count=2

#. Запрос списка объектов, у которы свойство string_text имеет значение example1

    .. code-block:: bash

        curl -X GET -u demo@local:ion-demo https://dnt.iondv.com/rest/crud/class_string@develop-and-test/?string_text=example1

#. Запрос списка объектов, у которы свойство string_text имеет значение example1, со смещением 1 и кол-вом 2

    .. code-block:: bash

        curl -X GET -u demo@local:ion-demo https://dnt.iondv.com/rest/crud/class_string@develop-and-test/?string_text=example1&_offset=1&_count=2

пример запроса к сервису crud для получения списка объектов с различными параметрами сдвига и фильтрации в :doc:`dnt <request_examples>`:
`test/modules/rest/crud.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/crud.spec.js>`_

.. code-block:: text

    /Checking crud service/GET/# getting a list of text objects, with an offset of 1 and a count of 2
    /Checking crud service/GET/# getting a list of text objects containing a specific string
