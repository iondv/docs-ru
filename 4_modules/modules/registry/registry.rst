Модуль Registry
===============

.. toctree::
   :hidden:
   :titlesonly:
   
   registry_code
   registry_treegrid


**Модуль регистра (registry)** – ключевой модуль, предназначенный непосредственно для работы с данными на основе структур метаданных – в том числе для ведения проектов, программ, мероприятий и др.

Настройка
---------


* :doc:`DI (treegridController) <registry_treegrid>`

Deploy
~~~~~~

Настройка частоты опроса в deploy.json
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Настройка частоты опроса сервера, что объект не заблокирован в deploy.json:

.. code-block:: js

   "registry": {
      "globals": {
         "notificationCheckInterval": 60000 // раз в минуту
      }
   }

Настройка createByCopy
^^^^^^^^^^^^^^^^^^^^^^

Настройка отображения кнопки "Создать еще" в deploy.json:

.. code-block:: js

   "createByCopy": [
             "person@khv-childzem" // класс
           ],

Фильтры
~~~~~~~

Подробнее о фильтрах :doc:`здесь </3_development/functionality/functionality_files/filter>`.

Настройка помощь по фильтрам
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Справка размещается в файле шаблона ``modules/registry/view/default/templates/view/list-filter-helper.ejs``

Требования к коду
-----------------

Cтиль написания компонентов фронт-енда :doc:`здесь <registry_code>`.

----
