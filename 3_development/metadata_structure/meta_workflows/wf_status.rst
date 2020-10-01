
Статусы бизнес-процесса
=======================

JSON
^^^^

.. code-block::

   "states": [
       {
         "name": "new",
         "caption": "Новое",
         "maxPeriod": null,
         "conditions": [],
         "itemPermissions": [],
         "propertyPermissions": [],
         "selectionProviders": []
       }
     ]

Описание полей
--------------

.. list-table::
   :header-rows: 1

   * - Поле
     - Описание
   * - ``"name"``
     - Системное имя статуса
   * - ``"caption"``
     - Логическое имя статуса
   * - ``"maxPeriod"``
     - *нет данных*
   * - ``"conditions"``
     - Условия для статуса БП. Задаются аналогично "Условиям отбора допустимых значений".
   * - ``"itemPermissions"``
     - Разрешения для объекта
   * - ``"propertyPermissions"``
     - Разрешения для свойств
   * - ``"selectionProviders"``
     - Выборка допустимых значений


----
