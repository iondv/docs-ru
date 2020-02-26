.. role:: raw-html-m2r(raw)
   :format: html


`Оглавление </docs/ru/index.md>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Назад: `Мета представлений - общая часть <meta_view_main.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Режим наложения
===============

Поле **Режим наложения** - ``"overrideMode"`` позволяет задать два значения ``"Перекрыть"`` и ``"Переопределить"``.

Настройка режимов наложения в мете представления:

**Тип 1** - ``"Переопределить"`` - переопределяет стандартный способ отображения соответствующих атрибутов заданных в мете представления класса. Атрибуты, которые не заданы в мете представления класса, отображаются стандартным образом на форме согласно заданной очередности по умолчанию.

**Тип 2** - ``"Перекрыть"`` - выводятся только атрибуты заданные в мете представления.

Пример
^^^^^^

.. code-block::

     "actions": null,
     "siblingFixBy": null,
     "siblingNavigateBy": null,
     "historyDisplayMode": 0,
     "collectionFilters": null,
     "version": null,
     "overrideMode": 1, 
     "commands": [

----

`Licence </LICENSE>`_ &ensp;  `Contact us <https://iondv.com/portal/contacts>`_ &ensp;  `English </docs/en/2_system_description/metadata_structure/meta_view/overridemode.md>`_   &ensp;
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved. 
