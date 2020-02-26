.. role:: raw-html-m2r(raw)
   :format: html


`Оглавление </docs/ru/index.md>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Предыдущая страница: `Статус бизнес-процесса <status_wf.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Переходы бизнес-процесса
========================

JSON
^^^^

.. code-block::

   "transitions": [
       {
         "name": "basic",
         "caption": "На согласование",
         "startState": "create",
         "finishState": "inAgreed",
         "signBefore": false,
         "signAfter": false,
         "roles": [],
         "assignments": [],
         "conditions": []
       }
     ]

Описание полей
--------------

.. list-table::
   :header-rows: 1

   * - Поле
     - Описание
   * - ``"name"``
     - Системное имя статуса.
   * - ``"caption"``
     - Логическое имя статуса.
   * - ``"startState"``
     - Начальный статус для осуществления перехода по БП.
   * - ``"finishState"``
     - Конечный статус по завершению перехода по БП.
   * - ``"signBefore"``
     - Логическое значение "Подписать до начала перехода".
   * - ``"signAfter"``
     - Логическое значение "Подписать по завершению перехода".
   * - ``"roles"``
     - Список ролей, с правами на осуществление перехода.
   * - ``"assignments"``
     - Присвоение значения атрибутам после осуществления перехода по БП.
   * - ``"conditions"``
     - Условия, выполняемые для осуществления перехода по БП. Задаются аналогично "Условиям отбора допустимых значений".


Присвоение значения атрибутам по ссылке
---------------------------------------

Задается через свойство ``"assignments"`` в переходе БП. 

Пример
^^^^^^

.. code-block::

   ...
        "assignments": [
           {
             "key": "resolution.stateRemPet",
             "value": "end"
           }
         ]
   ...

По ссылке атрибута типа "Ссылка" [resolution], для атрибута [stateRemPet] присвоить значение "end" - при выполнении данного перехода по БП.

Следующая страница: `Мета безопасности </docs/ru/2_system_description/metadata_structure/meta_security/meta_security.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

----

`Licence </LICENSE>`_ &ensp;  `Contact us <https://iondv.com/portal/contacts>`_ &ensp;  `English </docs/en/2_system_description/metadata_structure/meta_workflows/transitions_wf.md>`_   &ensp;
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved. 
