Мета классов - атрибутивная часть
=================================

.. toctree::
   :titlesonly:
   :hidden:
   
   property_types
   meta_class_attribute/attr_autoassigned
   meta_class_attribute/attr_cached_true
   meta_class_attribute/attr_default_value
   meta_class_attribute/attr_formula
   meta_class_attribute/attr_indexed
   meta_class_attribute/attr_itemclass_backcoll
   meta_class_attribute/attr_ref_backref
   meta_class_attribute/attr_selconditions
   meta_class_attribute/attr_selectionprovider
   meta_class_attribute/attr_selsorting
   meta_class_attribute/binding
   meta_class_attribute/eagerloading
   meta_class_attribute/semantic

**Атрибутивная часть меты класса** описывает поля атрибута класса. Атрибутов в классе обычно минимум два - ключевое поле и поле данных. Они содержатся в виде массива в поле ``"properties"`` основной части меты классов. Каждый атрибут - это объект следующей структуры:

JSON
----

.. code-block:: json

       {
         "orderNumber": 20,
         "name": "integer_integer",
         "caption": "Редактор целых чисел [14]",
         "type": 6,
         "size": null,
         "decimals": 0,
         "allowedFileTypes": null,
         "maxFileCount": 0,
         "nullable": true,
         "readonly": false,
         "indexed": false,
         "unique": false,
         "autoassigned": false,
         "hint": null,
         "defaultValue": null,
         "refClass": "",
         "itemsClass": "",
         "backRef": "",
         "backColl": "",
         "binding": "",
         "semantic": null,
         "selConditions": [],
         "selSorting": [],
         "selectionProvider": null,
         "indexSearch": false,
         "eagerLoading": false,
         "formula": null,
         "cached": true
       }

Описание полей
--------------

.. list-table::
   :header-rows: 1

   * - Код
     - Имя
     - Допустимые значения
     - Описание
   * - ``"orderNumber"``
     - **Порядковый номер**
     - Целое неотрицательное
     - Задает расположение атрибута относительно других атрибутов этого же класса.
   * - ``"name"``
     - **Системное имя**
     - Строка, только латиница без пробелов
     - Указывается имя атрибута, с которым будет работать система, а значит не может быть пустым, может содержитать только символовы латинского алфавита, без пробелов (задается один раз при создании атрибута). В последующем поменять имя нельзя.
   * - ``"caption"``
     - **Логическое имя**
     - Строка
     - Отображение имени атрибута в пользовательском интерфейсе.
   * - ``"type"``
     - **Тип**
     - Целое - идентификатор (код) типа
     - Тип данных атрибута. См. :doc:`Типы атрибутов </3_development/metadata_structure/meta_class/property_types>`
   * - ``"size"``
     - **Размер**
     - Целое положительное
     - Максимальный размер данных атрибута, допистимые значения зависят от типа атрибута.
   * - ``"decimals"``
     - **Число знаков после запятой**
     - Целое неотрицательное
     - Число знаков после запятой, задается только для типа "Десятичное [8]".
   * - ``"allowedFileTypes"``
     - **Допустимые типы файлов**
     - Массив строк
     - Позволяет задать допустимые расширения файлов, которые пользователь может загрузить в атрибут типа "Коллекция файлов [110]".
   * - ``"maxFileCount"``
     - **Максимальное количество файлов**
     - Число от 1 до 5
     - Задает максимальное количество файлов, которые пользователь может загрузить в атрибут типа "Коллекция файлов [110]".
   * - ``"nullable"``
     - **Допустимо пустое значение**
     - Логический
     - Разрешает или запрещает пустое значение атрибута.
   * - ``"readonly"``
     - **Только для чтения**
     - Логический
     - Разрешает или запрещает изменять значение атрибута.
   * - ``"indexed"``
     - :doc:`Индексация для поиска <meta_class_attribute/attr_indexed>`
     - Логический
     - Указывает, нужно ли индексировать значения данного атрибута для ускорения поиска.
   * - ``"unique"``
     - **Уникальные значения**
     - Логический
     - Для атрибута накладывает ограничение уникальности (\ **Внимание**\ : нельзя создать два объекта класса с одинаковыми значениями в уникальном атрибуте).
   * - ``"autoassigned"``
     - :doc:`Автозаполнение <meta_class_attribute/attr_autoassigned>`
     - Логический
     - Разрешает или запрещает автоматическое заполнение поля приложением.
   * - ``"hint"``
     - **Подсказка**
     - Строка
     - Задает сообщение, которые выведется в пользовательском интерфейсе рядом с именем атрибута.
   * - ``"defaultValue"``
     - :doc:`Значение по умолчанию <meta_class_attribute/attr_default_value>`
     - Зависит от типа атрибута
     - Указывается значение, которое будет заполнено в атрибуте в форме создания (при создании объекта).
   * - ``"refClass"``
     - :doc:`Атрибут ссылки <meta_class_attribute/attr_ref_backref>`
     - Строка, только латиница, без пробелов
     - Содержит значение поля ``"name"`` (Системное имя) класса, который должен использоваться в атрибуте типа "Ссылка [13]".
   * - ``"itemsClass"``
     - :doc:`Атрибут коллекции <meta_class_attribute/attr_itemclass_backcoll>`
     - Строка, только латиница без пробелов
     - Содержит значение поля ``"name"`` (Системное имя) класса, объекты которого могут привязаться к атрибуту типа "Коллекция [14]"
   * - ``"backRef"``
     - :doc:`Атрибут обратной ссылки <meta_class_attribute/attr_ref_backref>`
     - Строка, только латиница без пробелов
     - Указывается атрибут типа "Ссылка [13]", из класса, указанного в свойстве Класс коллекции, который ссылается на исходный класс. Нужно для фильтрации и привязки объектов из класса Класс коллекции по значению ссылочного атрибута.
   * - ``"backColl"``
     - :doc:`Атрибут обратной коллекции <meta_class_attribute/attr_itemclass_backcoll>`
     - Строка, только латиница без пробелов
     - Указывается атрибут типа "Коллекция [14]", из класса, указанного в свойстве Класс коллекции, который ссылается на исходный класс. Нужно для фильтрации и привязки объектов из класса Класс коллекции по значению ссылочного атрибута.
   * - ``"binding"``
     - :doc:`Основание коллекции <meta_class_attribute/binding>`
     - Строка, только латиница без пробелов
     - Указывается атрибут класса, к которому привязывается атрибут обратной ссылки. Если не указан, то принимается ключевой атрибут.
   * - ``"semantic"``
     - :doc:`Семантика <meta_class_attribute/semantic>`
     - Строка
     - Указывается для ссылочных атрибутов для того, чтобы выводить и формировать информацию из ссылочного класса, корректную для описания артибута в объекте исходного класса.
   * - ``"selConditions"``
     - :doc:`Условия отбора допустимых значений <meta_class_attribute/attr_selconditions>`
     - Null либо массив объектов
     - Позволяет ограничить выбор объектов по ссылке, допустимых для привязкки в данном ссылочном атрибуте.
   * - ``"selSorting"``
     - :doc:`Сортировка выборки допустимых значений <meta_class_attribute/attr_selsorting>`
     - Null либо массив объектов
     - Позволяет сортировать выбор объектов по ссылке, допустимых для привязкки в данном ссылочном атрибуте.
   * - ``"selectionProvider"``
     - :doc:`Список выбора допустимых значений <meta_class_attribute/attr_selectionprovider>`
     - Null либо объект
     - Задает список выбора допустимых значений для атрибута.
   * - ``"indexSearch"``
     - **Полнотекстовый поиск**
     - Логический
     - Признак использования атрибута в полнотекстовом поиске. Указывает, что значение данного атрибута должно индексироваться поисковой системой. См. :doc:`Индексация <meta_class_attribute/attr_indexed>`
   * - ``"eagerLoading"``
     - :doc:`Жадная загрузка <meta_class_attribute/eagerloading>`
     - Логический
     - Загрузка достаточного объема данных объекта по ссылке (для атрибутов типа ссылка и коллекция).
   * - ``"formula"``
     - :doc:`Вычисляемые поля <meta_class_attribute/attr_formula>`
     - Null либо объект
     - Указывает на формулу расчета.
   * - ``"cached"``
     - :doc:`Кеширование значения вычислимого атрибута <meta_class_attribute/attr_cached_true>`
     - Логический
     - Применяется только для значений атрибута, полученных с помощью вычисления по формуле. Указывает на возможность кеширования значения вычислимого атрибута.

----
