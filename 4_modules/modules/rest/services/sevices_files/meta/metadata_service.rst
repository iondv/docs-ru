Cервис публикации метаданных Meta
===================================

**Meta** ``meta`` - встроенный сервис в rest модуле, который предоставляет доступ к интерфейсу метарепозитория в формате веб-сервиса.

Сервис требует подключения в ``deploy.json`` и обязательного указания ``options.dataRepo`` и ``options.metaRepo``, пример:

.. code-block:: js

    "meta": {
            "module": "modules/rest/lib/impl/meta",
            "options": {
              "dataRepo": "ion://dataRepo",
              "metaRepo": "ion://metaRepo"
            }
    }

Поддерживаются все `типы авторизации </4_modules/modules/rest/authorization/authorization.rst>`_, по умолчанию - авторизация учетными данными.

Сервис предоставляет доступ к следующим **GET** запросам:

* Получение информации о классе метаданных: `getMeta <meta_getMeta.rst>`_
* Получение списка всех классов метаданных: `listMeta <meta_listMeta.rst>`_
* Получение информации о классе-предке: `ancestor <meta_ancestor.rst>`_
* Получение информации о свойствах объектов класса: `propertyMetas <meta_propertyMetas.rst>`_
* Получение списка секций навигации: `getNavigationSections <meta_getNavigationSections.rst>`_
* Получение информации о секции навигации: `getNavigationSection <meta_getNavigationSection.rst>`_
* Получение информации об узле навигации: `getNode <meta_getNode.rst>`_
* Получение списка узлов навигации в секции: `getNodes <meta_getNodes.rst>`_
* Получение информации о списочной форме представления объектов класса: `getListViewModel <meta_getListViewModel.rst>`_
* Получение информации о форме представления объектов класса в виде коллекции: `getCollectionViewModel <meta_getCollectionViewModel.rst>`_
* Получение информации о форме представления объектов класса при редактировании: `getItemViewModel <meta_getItemViewModel.rst>`_
* Получение информации о форме представления объектов класса при создании: `getCreationViewModel <meta_getCreationViewModel.rst>`_
* Получение информации о форме представления объектов класса при просмотре: `getDetailViewModel <meta_getDetailViewModel.rst>`_
* Получение списка возможных бизнес-процессов для класса: `getWorkflows <meta_getWorkflows.rst>`_
* Получение информации о форме представления объекта класса при некотором состоянии бизнес-процесса: `getWorkflowView <meta_getWorkflowView.rst>`_
* Получение информации о бизнес-процессе класса: `getWorkflow <meta_getWorkflow.rst>`_
* Получение информации о маске формы представления: `getMask <meta_getMask.rst>`_
* Получение списка доступных валидаторов ввода: `getValidators <meta_getValidators.rst>`_
