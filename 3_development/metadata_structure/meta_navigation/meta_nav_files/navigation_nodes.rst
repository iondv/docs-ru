Мета узлов навигации
====================

JSON
----

.. code-block:: js

   {
     "code": "classDatetime",
     "orderNumber": 0,
     "type": 1,
     "caption": "Класс \"Дата/Время [9]\"",
     "classname": "classDatetime",
     "container": null,
     "collection": null,
     "url": null,
     "external": true,
     "hint": null,
     "conditions": [],
     "sorting": [],
     "eagerLoading": {
        "list": { // Здесь задается жадная загрузка для списков
           "internet": ["okato"],
           "someClass1": ["refAttr1", "refAttr2.refAttr3"],
           "someClass2": ["colAttr4"]
        },
        "item": { // Здесь задается жадная загрузка для форм редактирования
           "internet": ["okato", "standart"],
           "someClass1": ["refAttr1", "refAttr2.refAttr3", "refAttr5", "colAttr4"],
           "someClass2": ["colAttr4"]
        }
      },
     "pathChains": [],
     "searchOptions": null
     "metaVersion": "2.0.7"
   }

Описание полей
--------------

.. list-table::
   :header-rows: 1

   * - Поле
     - Наименование
     - Допустимые значения
     - Описание
   * - ``"code"``
     - **Системное имя**
     - Строка латиницей, без пробелов
     - Системное имя узла навигации может быть составным, если принадлежит узлу навигации типа Группа [0].
   * - ``"orderNumber"``
     - **Порядковый номер**
     - Целое число
     - Задает порядок сортировки пунктов меню в пределах секции навигации
   * - ``"type"``
     - **Тип**
     - Целое число
     - Задает логику работы пункта меню, выводимые при переходе/активации значения. Накладывает ограничения на прочие поля меты узла навигации.
   * - 
     - 
     - 0
     - *Группа.* Объединяет в себе другие узлы навигации по какому-либо общему признаку, не является страницей класса.
   * - 
     - 
     - 1
     - *Страница класса.* Отображает структуру и объекты класса, заданного в поле "classname".
   * - 
     - 
     - 2
     - *Страница контейнера.* Выполняет отображение списка объектов в коллекции. Для таких узлов навигации нужно указывать класс и идентификатор объекта-контейнера, а также имя атрибута коллекции.                                                                    
   * - 
     - 
     - 3
     - *Гиперссылка.* Осуществляет переход на ссылку, заданную в поле "url"
   * - ``"title"``
     - `\ Заголовок <title.rst>`_
     - Строка
     - Позволяет дополнительно указать заголовок страницы.
   * - ``"caption"``
     - **Логическое имя**
     - Строка
     - Наименование узла навигации отображаемое в интерфейсе.
   * - ``"classname"``
     - **Класс**
     - Строка латиницей, без пробелов
     - Если "Тип" - "Страница класса (1)", то поле обязательно к заполнению.
   * - ``"container"``
     - **ID контейнера**
     - Строка или null
     - Идентификатор объекта содержащего коллекцию отображаемую на странице.
   * - ``"collection"``
     - **Атрибут коллекции**
     - Строка или null
     - Имя атрибута коллекции, содержимое которого надо вывести на странице.
   * - ``"url"``
     - **URL**
     - Гиперссылка (принимает любые строки)
     - Если "Тип" - "Гиперссылка (3)", то поле обязательно к заполнению.
   * - ``"external"``
     - **Признак внешнего ресурса**
     - Логический
     - Открывает страницу по ссылке в новом окне, если присвоено значение ``true``.
   * - ``"hint"``
     - **Подсказка**
     - Строка
     - Текст, заданный в этой строке, отображается при наведении на узел навигации, которому она принадлежит.
   * - ``"conditions"``
     - `\ Условия выборки <conditions.rst>`_
     - Массив объектов
     - Фильтр при открытии списка объектов. Используется для узлов типа «Страница класса» и «Страница контейнера».
   * - ``"sorting"``
     - **Сортировка**
     - Массив объектов
     - Используется для узлов типа «Страница класса» и «Страница контейнера». Здесь задаются параметры сортировки объектов в списке. Параметры задаются аналогично настройкам сортировки и выборки допустимых значений в атрибутах.
   * - ``"eagerLoading"``
     - **Жадная загрузка**
     - Объект
     - Настройка жадной загрузки в навигации. Если нужна ЖЗ для класса по всем навигациям, то правильнее ее задавать в файле deploy.json. Поэтому данный параметр используется редко.
   * - ``"pathChains"``
     - **Хлебные крошки**
     - Массив объектов
     - Здесь задается логика формирования «иерархической» навигации от страницы объекта к вышестоящим объектам. Может быть использовано конкретной реализацией ION-приложения для оптимизации навигации.
   * - ``"searchOptions"``
     - **Поиск в узле навигации**
     - Массив объектов
     - На уровне класса определяет как искать объекты класса из представления списка: по вхождению слов или полные слова, по отдельным атрибутам или по указанным атрибутам в списке с параметрами поиска через пробел.
   * - ``"metaVersion"``
     - **Версия меты**
     - Строка
     - Версия метаданных.


Настройка поиска в узле навигации
---------------------------------

.. code-block:: js

      "searchOptions": {
       "person": {
         "searchBy": [ // атрибуты по которым ищем, по умолчанию то, что выводится в колонках
           "surname",
           "name",
           "patronymic"
         ],
         "splitBy": "\\s+", // разбивать поисковую фразу на регулярное выражение, части сопоставить с атрибутами
         "mode": ["starts", "starts", "starts"], // режимы сопоставления - в данном случае "начинается с" (доступны like, contains, starts, ends)
         "joinBy": "and" // режим объединения условий на атрибуты (по умолчанию or)
       }
      }

Структура в mongoDB (registry)
------------------------------

.. code-block:: json

   {
       "_id" : ObjectId("578f07aa0ce0024ce143e71e"),
       "code" : "classDatetime",
       "orderNumber" : 0,
       "type" : 1,
       "caption" : "Класс \"Дата/Время [9]\"",
       "classname" : "classDatetime",
       "container" : null,
       "collection" : null,
       "url" : null,
       "hint" : null,
       "conditions" : [],
       "sorting" : [],
       "pathChains" : [],
       "itemType" : "node",
       "section" : "simpleTypes",
       "namespace" : ""
   }


----
