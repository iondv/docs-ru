Мета навигации
==============

**Мета навигации** - регулирует расположение элементов в навигационном блоке. 

Мета навигации разделяется на **мету узлов навигации** и **мету секции навигации**. 

Мета секций навигации
---------------------

:doc:`Мета секций навигации <meta_nav_files/navigation_section>` состоит из поля ``"name" + .section.json`` и находится в директории ``navigation``. 

*Например*: ``workflow.section.json``. 

Мета узлов навигации
--------------------

:doc:`Мета узлов навигации <meta_nav_files/navigation_nodes>` состоит из:

* Для узлов навигации первого порядка - тех узлов, которые находятся непосредственно в секции навигации: поле ``"code"`` + ``.json`` и находится в директории, имя которой совпадает с именем файла секции навигации к которому относится узел навигации. 

*Например*\ : В директории ``navigation`` есть файл секции навигации ``simpleTypes.section.json``. И есть узел навигации ``classString.json``\ , который размещается в секции ``simpleTypes``. Файл узла навигации будет иметь путь: ``navigation\simpleTypes\classString.json``.

* Для узлов навигации второго порядка - тех узлов, которые входят в группу (особый тип узлов навигации, поле ``"type"`` в которых содержит значение ``0``\ ). 
  Разница в том, что поле ``"code"`` у таких узлов составное и состоит из поля ``"code"`` группы и личного наименования. 

*Например*\ : ``navigation\relations\classReference.refBase.json``. Это файл узла навигации ``refBase``\ , который находится в группе ``classReferense`` секции навигации ``relations``.


.. toctree::
   :titlesonly:
   
   meta_nav_files/conditions
   meta_nav_files/navigation_nodes
   meta_nav_files/navigation_section
   meta_nav_files/title


----
