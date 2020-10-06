Модуль Registry
=================


**Модуль регистра (registry)** – ключевой модуль, предназначенный непосредственно для работы с данными на основе структур метаданных – в том числе для ведения проектов, программ, мероприятий и др.

Настройка
---------


* `DI (treegridController) <registry_treegrid.rst>`_

Deploy
^^^^^^

Настройка частоты опроса в deploy.json
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Настройка частоты опроса сервера, что объект не заблокирован в deploy.json:

.. code-block::

   "registry": {
      "globals": {
         "notificationCheckInterval": 60000 // раз в минуту
      }
   }

Настройка createByCopy
^^^^^^^^^^^^^^^^^^^^^^

Настройка отображения кнопки "Создать еще" в deploy.json:

.. code-block::

   "createByCopy": [
             "person@khv-childzem" // класс
           ],

Фильтры
-------

Подробнее о фильтрах `здесь </3_development/functionality/functionality_files/filter.rst>`_.

Настройка помощь по фильтрам
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Справка размещается в файле шаблона ``modules/registry/view/default/templates/view/list-filter-helper.ejs``

Требования к коду
-----------------

Cтиль написания компонентов фронт-енда `здесь <registry_code.rst>`_

----
