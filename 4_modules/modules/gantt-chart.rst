Модуль Gantt-chart
====================


**Модуль диаграм ганта (gantt-chart)** – модуль, предназначенный для вывода специфичных типов иерархических данных, имеющих даты.

Конфигурация в deploy
---------------------

Указание длины поисковой выдачи
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: text

    "searchCount": 25

Добавление фильтров на колонки
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: text

   "gantt-chart": {
         "globals": {
           "config": {
             "columns": [
               {
                 "name": "text",
                 "caption": "Название"
               },
               {
                 "name": "owner",
                 "caption": "Владелец",
                 "align": "center",
                 "filter": true
               },
               {
                 "name": "priority",
                 "caption": "Приоритет",
                 "align": "center",
                 "filter": true
               },

Указание для разных классов разные createUrl
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: js

    "createUrl": {
               "project@project-management": "registry/project-management@eventBasic/new/eventBasic",
               "event@project-management": "registry/project-management@eventBasic/new/eventBasic",
               "eventObject@project-management": "registry/project-management@eventOnly/new/eventOnly",
               "eventOnly@project-management": "registry/project-management@eventOnly/new/eventOnly",
               "projectKNA704@project-management": "registry/project-management@eventKNA704/new/eventKNA704",
               "eventKNA704@project-management": "registry/project-management@eventOnlyKNA704/new/eventOnlyKNA704",
               "eventObjectKNA704@project-management": "registry/project-management@eventOnlyKNA704/new/eventOnlyKNA704",
               "eventOnlyKNA704@project-management": "registry/project-management@eventOnlyKNA704/new/eventOnlyKNA704"
             }

Настройки видов представлений
-----------------------------

.. code-block:: js

    "preConfigurations": {
               "config1": {
                 "caption": "Основная",
                 "showPlan": true,
                 "units": "month",
                 "step": 3,
                 "days_mode": "full",
                 "hours_mode": "full",
                 "default": true
               },
               "config2": {
                 "caption": "Расширенная",
                 "showPlan": false,
                 "units": "year",
                 "days_mode": "full",
                 "hours_mode": "work",
                 "columnDisplay": {
                   "text": true,
                   "owner": true
                 },
                 "filters": {
                   "priority": "Высокий"
                 }
               },
               "config3": {
                 "caption": "Обзорная",
                 "showPlan": true,
                 "units": "year",
                 "step": 5,
                 "days_mode": "full",
                 "hours_mode": "full",
                 "columnDisplay": {
                   "text": true,
                   "owner": true,
                   "priority": true
                 },
                 "filters": {
                   "priority": "Обычный"
                 }
               }
             }

В поле ``filters`` - задаем свойство и значения для фильтра

Настраиваемый фильтр при выборке подузлов
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

В формулах в общем синтаксисе выражений теперь можно обращаться к данным контекста. Пока реализовано только для списков в регистри и ганте. По мере перехода на общий синтаксис реализуем поддержку повсеместно в ядре.

Настраиваемый фильтр не применяется к корневому обьекту явно указанному через параметр урла, или выбранный в выпадающем списке. Фильтр применяется только при ВЫБОРКЕ ПОДУЗЛОВ.

Сортировка выдачи
~~~~~~~~~~~~~~~~~

При выводе проекта, в них мероприятия сортируются по атрибуту numEvent - на всех уровнях иерархии.

.. code-block:: text

   "sortBy": "numEvent"

   // либо
   "sortBy": {"numEvent": -1, "anyOtherAttr": 1}

Настройка списка выбора объекта для вывода информации
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Применяется при условии настроенного фильтра для колонки и позволяет не отображать все объекты сразу, а выбирать из списка. Если значение ``"rootParamNeeded:true"`` - выводится пустой экран и окно для выбора проекта.

.. code-block:: js

   "gantt-chart": {
         "globals": {
           "rootParamNeeded": true
         }
       }

----
