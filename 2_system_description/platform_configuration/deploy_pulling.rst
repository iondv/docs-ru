.. role:: raw-html-m2r(raw)
   :format: html


Сборка deploy из отдельных файлов
=================================
:doc:`Оглавление <../../index>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. cНазад: :doc:`Функциональность <functionality>`
.. c^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Разделение файла конфигурации deploy.json
-----------------------------------------

Для удобства организации и повышения читаемости конфигурации приложения в deploy.json есть возможность разделить этот файл на несколько отдельных файлов конфигурации.

Варианты разделения могут быть любыми - можно вынести из него только конфигурацию модулей приложения или описывать каждый объект deploy в отдельном файле.

Для конфигурации в папке deploy приложения нужно поместить произвольные файлы с расширениями .json или .yml.

Для корректной работы в них необходимо сохранить изначальную структуру deploy.json - объекты должны быть вложены друг в друга в том же порядке, что в исходном файле. Исключение - модули приложения.

Например, если в deploy.json был определен объект globals.jobs.ticketClose.di, то для вынесения объекта di в отдельный файл в этом файле должна быть воспроизведена структура этих вложенных объектов:

.. code-block:: yaml

   ---
   globals:
     jobs:
       ticketClose:
         di:
           ticketCloser:
             executable: applications/khv-ticket-discount/lib/overnightTicketClose
             options:
               dataRepo: ion://dataRepo
               log: ion://sysLog
               workflows: ion://workflows

Файлы конфигурации модулей
--------------------------

В случае конфигов модулей, их можно также

#. Разместить в директориях deploy/modules/<имя модуля>/
#. Вынести конфиг для модуля целиком в файл deploy/modules/<имя модуля>.yml (.json)

Описание при этом начинается с корня модуля (а не приложения):

.. code-block:: yaml

   ---
   globals:
     navigation:
       namespaces:
         khv-ticket-discount: Льготные билеты
     eagerLoading:
       "*":
         applicant@khv-ticket-discount:
           item:
             - documents.vidDocument
         flight@khv-ticket-discount:
           list:
             - route.pointDeparture
             - route.pointArrival
     listSearchOptions:
       ticketYear@khv-ticket-discount:
         "*":
           searchBy:
             - flight
             - person
             - numberTicket
             - area
           refDepth: 3
        flight@khv-ticket-discount:
         "*":
           searchBy:
             - route
             - number
           refDepth: 3
     di:
       pmListToDocx:
         module: modules/registry/export/listToDocx
          initMethod: init
         initLevel: 0
         options:
           tplDir: applications/khv-ticket-discount/export/list
           log: ion://sysLog
           injectors:
             - ion://monthTicketStatsInjector
   ...

----

`License <https://github.com/iondv/framework/blob/master/LICENSE>`_                                        `Contact us <https://iondv.com/portal/contacts>`_                                         `English <https://iondv.readthedocs.io/en/latest/index.html>`_
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


.. raw:: html

   <div><img src="https://mc.iondv.com/watch/local/docs/framework" style="position:absolute; left:-9999px;" height=1 width=1 alt="iondv metrics"></div>


----

Copyright (c) 2018 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved.
