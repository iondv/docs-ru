Cервис публикации метаданных Meta
=================================

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

Поддерживаются все :doc:`типы авторизации </4_modules/modules/rest/authorization/authorization>`, по умолчанию - авторизация учетными данными.

Сервис предоставляет доступ к следующим **GET** запросам:
---------------------------------------------------------

.. toctree::
   :titlesonly:
   
   meta_getMeta
   meta_listMeta
   meta_ancestor
   meta_propertyMetas
   meta_getNavigationSections
   meta_getNavigationSection
   meta_getNode
   meta_getNodes
   meta_getListViewModel
   meta_getCollectionViewModel
   meta_getCreationViewModel
   meta_getItemViewModel
   meta_getDetailViewModel
   meta_getWorkflows
   meta_getWorkflowView
   meta_getWorkflow
   meta_getMask
   meta_getValidators
   
.. toctree::
   :hidden:
   :titlesonly:
   
   meta_query_parameters

