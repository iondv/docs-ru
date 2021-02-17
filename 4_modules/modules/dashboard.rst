Модуль Панель управления (dashboard)
====================================


**Модуль дашбоарда (dashboard)** – модуль для выведения краткой информации в виде блоков. Основывается на модели виджетов.

Структура модуля
----------------

Панель управления состоит из трех базовых сущностей - **менеджер**, **макет** и **виджет**.

Менеджер (manager)
~~~~~~~~~~~~~~~~~~

**Менеджер** - это основной компонент модуля, отвечающий за создание и инициализацию виджетов, макетов, подключение панели к другим модулям.

.. code-block:: js

   let manager = require('modules/dashboard/manager');

Макет (layout)
~~~~~~~~~~~~~~

**Макет** - это EJS шаблон, в котором определяются схема размещения виджетов, параметры ддя шаблонов виджетов, плагин для управления сеткой макета на клиенте (например gridster), подключаются общие ресурсы.\

Базовые макеты модуля находятся в папке /dashboard/layouts. Опубликованные из мета-данных в папке /applications/${meta-namespace}/layouts.\ 

Каждый макет имеет уникальный ID. При публикации макета из меты к ID добавляется префикс. 

.. code-block:: js

   let dashboard = require('modules/dashboard');
   dashboard.getLayout('demo');
   dashboard.getLayout('develop-and-test-demo');

При рендере макета необходимо передать объект manager.

.. code-block:: js

   res.render(dashboard.getLayout('demo'), { dashboard });

Виджет (widget)
~~~~~~~~~~~~~~~

**Виджет** - это объект, который размещается на макете и взаимодействует с сервером через ajax-запросы. 

Базовые виджеты модуля находятся в папке /dashboard/widgets. Опубликованные из мета-данных в папке /applications/${meta-namespace}/widgets.  

Виджет состоит из файла класса **index.js** и шаблона представления **view.ejs**.
Класс должен наследоваться от базового класса /dashboard/base-widget или его потомков.


* Метод **init()** отвечает за начальную инициализацию виджета при старте сервера.
* Метод **refresh()** вызывается при получении ajax-запроса от клиента. 
* Метод **job()** получает данные для виджета.

Каждый виджет имеет уникальный ID. При публикации виджета из меты к ID добавляется префикс.

.. code-block:: js

   dashboard.getWidget('demo');
   dashboard.getWidget('develop-and-test-demo');

При рендере представления виджета необходимо передать объект widget.

.. code-block:: html

   <% var widget = dashboard.getWidget('develop-and-test-demo') %>
   <%- partial(widget.view, {widget}) %>

Публикация из меты
------------------

Пример структуры в applications/develop-and-test

.. code-block:: text

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

Для того, чтобы данные из меты подгружались в модуль дашборда, необходимо в файле конфигурации приложения
``deploy.json`` добавить следующую секцию, в раздел ``"modules"``\ :

.. code-block:: js

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
