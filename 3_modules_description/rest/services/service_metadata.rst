
Cервис публикации метаданных
============================

Сервис ``meta`` - встроенный сервис в rest модуле, который предоставляет доступ к интерфейсу метарепозитория в формате веб-сервиса.

Сервис требует подключения в ``deploy.json`` и обязательного указания ``options.dataRepo`` и ``options.metaRepo``, пример:

.. code-block:: js

    "meta": {
            "module": "modules/rest/lib/impl/meta",
            "options": {
              "dataRepo": "ion://dataRepo",
              "metaRepo": "ion://metaRepo"
            }
    }

Поддерживаются все типы авторизации, по умолчанию - авторизация учетными данными.

Сервис предоставляет доступ к следующим **GET** запросам:

.. toctree::
    :titlesonly:

    Получение информации о классе метаданных: getMeta <meta_getMeta>
    Получение списка всех классов метаданных: listMeta <meta_listMeta>
    Получение информации о классе-предке: ancestor <meta_ancestor>
    Получение информации о свойствах объектов класса: propertyMetas <meta_propertyMetas>
    Получение списка секций навигации: getNavigationSections <meta_getNavigationSections>
    Получение информации о секции навигации: getNavigationSection <meta_getNavigationSection>
    Получение информации об узле навигации: getNode <meta_getNode>
    Получение списка узлов навигации в секции: getNodes <meta_getNodes>
    Получение информации о списочной форме представления объектов класса: getListViewModel <meta_getListViewModel>
    Получение информации о форме представления объектов класса в виде коллекции: getCollectionViewModel <meta_getCollectionViewModel>
    Получение информации о форме представления объектов класса при редактировании: getItemViewModel <meta_getItemViewModel>
    Получение информации о форме представления объектов класса при создании: getCreationViewModel <meta_getCreationViewModel>
    Получение информации о форме представления объектов класса при просмотре: getDetailViewModel <meta_getDetailViewModel>
    Получение списка возможных бизнес-процессов для класса: getWorkflows <meta_getWorkflows>
    Получение информации о форме представления объекта класса при некотором состоянии бизнес-процесса: getWorkflowView <meta_getWorkflowView>
    Получение информации о бизнес-процессе класса: getWorkflow <meta_getWorkflow>
    /getMask/:name
    /getValidators

#. **Запросы** осуществляются через GET-методы. 
#. **Имена методов** метарепозитория задаются через путь.
#. **Идентификаторы мета-объектов** также через путь, вторым уровнем. 
#. **Дополнительные аргументы** - как query параметры.

Список GET-методов:

.. code-block:: text

   /getMeta/:name
   /listMeta
   /ancestor/:classname
   /propertyMetas/:classname
   /getNavigationSections
   /getNavigationSection/:code
   /getNode/:code
   /getNodes/:section
   /getListViewModel/:classname
   /getCollectionViewModel/:classname
   /getItemViewModel/:classname
   /getCreationViewModel/:classname
   /getDetailViewModel/:classname
   /getWorkflows/:classname
   /getWorkflowView/:classname/:workflow/:state
   /getWorkflow/:classname/:workflow
   /getMask/:name
   /getValidators
