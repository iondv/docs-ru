.. role:: raw-html-m2r(raw)
   :format: html

Модуль Панель управления (dashboard)
====================================
`Оглавление </docs/ru/index.md>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Назад: `Модули <modules.md>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Модуль дашбоарда (dashboard)** – модуль предназначенный для выведения краткой информации в виде блоков. При этом дашбоард основывается на модели виджетов.

Структура модуля
----------------

Панель управления состоит из трех базовых сущностей - менеджер, макет и виджет.

Менеджер (manager)
^^^^^^^^^^^^^^^^^^

Менеджер - это основной компонент модуля, отвечающий за создание и инициализаци виджетов, макетов, подключение панели к другим модулям.

.. code-block::

   let manager = require('modules/dashboard/manager');

Макет (layout)
^^^^^^^^^^^^^^

Макет - это EJS шаблон, в котором определяются схема размешения виджетов, параметры ддя шаблонов виджетов, плагин для управления сеткой макета на клиенте (например gridster), подключаются общие ресурсы.\ :raw-html-m2r:`<br>`
Базовые макеты модуля находятся в папке /dashboard/layouts. Опубликованные из мета-данных в папке /applications/${meta-namespace}/layouts.\ :raw-html-m2r:`<br>`
Каждый макет имеет уникальный ID. При публикации макета из меты к ID добавляется префикс. 

.. code-block::

   let dashboard = require('modules/dashboard');
   dashboard.getLayout('demo');
   dashboard.getLayout('develop-and-test-demo');

При рендере макета необходимо передать объект manager.

.. code-block::

   res.render(dashboard.getLayout('demo'), { dashboard });

Виджет (widget)
^^^^^^^^^^^^^^^

Виджет - это объект, который размещается на макете и взаимодействует с сервером через ajax-запросы. 

Базовые виджеты модуля находятся в папке /dashboard/widgets. Опубликованные из мета-данных в папке /applications/${meta-namespace}/widgets.  

Виджет состоит из файла класса **index.js** и шаблона представления **view.ejs**.
Класс должен наследоваться от базового класса /dashboard/base-widget или его потомков.


* Метод **init()** отвечает за начальную инициализацию виджета при старте сервера.
* Метод **refresh()** вызывается при получении ajax-запроса от клиента. 
* Метод **job()** получает данные для виджета.

Каждый виджет имеет уникальный ID. При публикации виджета из меты к ID добавляется префикс.

.. code-block::

   dashboard.getWidget('demo');
   dashboard.getWidget('develop-and-test-demo');

При рендере представления виджета необходимо передать объект widget.

.. code-block::

   <% var widget = dashboard.getWidget('develop-and-test-demo') %>
   <%- partial(widget.view, {widget}) %>

Публикация из меты
------------------

Пример структуры в applications/develop-and-test

.. code-block:: sh

       dashboard
           layouts
             demo-layout
           widgets
             demo-widget
               index.js
               view.ejs
           static
               layouts              
               widgets
                 demo-widget

Для того что бы данные из меты подгружались в модуль дашборда, необходимо в файле конфигурации приложения
``deploy.json`` добавить следующую секцию, в раздел ``"modules"``\ :

.. code-block::

       "dashboard": {
         "globals": {
           "namespaces": {
             "develop-and-test": "Мета для тестирования и разработки"
           },
           "root": {
             "develop-and-test": "applications/develop-and-test/dashboard"
           }
         }
       }

----

`Licence </LICENSE>`_\ &ensp;  `Contact us <https://iondv.com/portal/contacts>`_ &ensp;  `English </docs/en/3_modules_description/dashboard.md>`_ &ensp;
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV".**\ :raw-html-m2r:`<br>`
All rights reserved. 
