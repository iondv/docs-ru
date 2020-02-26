.. role:: raw-html-m2r(raw)
   :format: html


`Оглавление </docs/ru/index.md>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Предыдущая страница: `Мета бизнес-процесса <meta_workflows.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

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


Следующая страница: `Переходы бизнес-процесса <transitions_wf.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

----

`Licence </LICENSE>`_ &ensp;  `Contact us <https://iondv.com/portal/contacts>`_ &ensp;  `English </docs/en/2_system_description/metadata_structure/meta_workflows/status_wf.md>`_   &ensp;
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved. 
