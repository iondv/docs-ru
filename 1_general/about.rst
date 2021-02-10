.. raw:: html

   <h1 align="center"> <a href="https://www.iondv.com/"><img src="https://raw.githubusercontent.com/iondv/docs-ru/master/_static/images/ION_logo_black_mini.png" alt="IONDV. Framework logo" width="600" align="center"></a>
   </h1>



.. raw:: html

   <h4 align="center">JS framework for rapid business application development</h4>



.. raw:: html

   <p align="center">
   <a href="http://www.apache.org/licenses/LICENSE-2.0"><img src="https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg?style=flat" alt="license" title=""></a>
   </p>



.. raw:: html

   <div align="center">
     <h3>
       <a href="https://www.iondv.com/" target="_blank">
         Website
       </a>
       <span> | </span>
       <a href="https://github.com/iondv/framework" target="_blank">
         Get it Free
       </a>
       <span> | </span>
       <a href="https://iondv.readthedocs.io/ru/latest/" target="_blank">
         Documentation
       </a>
     </h3>
   </div>



.. raw:: html

   <p align="center">
   <a href="https://twitter.com/ion_dv" target="_blank"><img src="https://raw.githubusercontent.com/iondv/docs-ru/master/_static/images/twitter.png" height="24px" alt="Twitter" title=""></a>
   <a href="https://www.facebook.com/iondv/" target="_blank"><img src="https://raw.githubusercontent.com/iondv/docs-ru/master/_static/images/facebook.png" height="24px" margin-left="20px" alt="Facebook" title=""></a>
   <a href="https://www.linkedin.com/company/iondv/" target="_blank"><img src="https://raw.githubusercontent.com/iondv/docs-ru/master/_static/images/linkedin.png" height="24px" margin-left="20px" alt="LinkedIn" title=""></a>
   <a href="https://www.instagram.com/iondv/" target="_blank"><img src="https://raw.githubusercontent.com/iondv/docs-ru/master/_static/images/Insta.png" height="24px" margin-left="20px" alt="Instagram" title=""></a>
   <a href="https://www.youtube.com/channel/UC_r2CGcOTfuV-7AXl6MwOqw" target="_blank"><img src="https://raw.githubusercontent.com/iondv/docs-ru/master/_static/images/youtube.png" height="24px" margin-left="20px" alt="Youtube" title=""></a>
   </p>


1. О IONDV. Framework
=====================

IONDV. Framework - это опенсорный фреймворк на node.js для разработки учетных приложений на основе метаданных в формате JSON/YAML
и отдельных функциональных модулей. Визуальный редактор `IONDV. Studio <https://studio.iondv.com>`_ позволяет создавать приложения по
технологии "no code" и собирать приложение с веб-сервисами REST-API (модуль `rest <https://github.com/iondv/rest>`_).
Ключевой модуль `registry <https://github.com/iondv/registry>`_ является универсальным средством представления и
редактирования данных, обработки их по бизнес-процессам.

На видео технология разработки и сборки приложения

.. raw:: html

   <iframe width="560" height="315" src="https://www.youtube.com/embed/s7q9_YXkeEo" frameborder="0" allowfullscreen></iframe>


Бесплатные demo-версии
----------------------

Посмотрите наши демо уже сейчас:

* `Studio <https://studio.iondv.com/index>`_ - специализированная IDE, созданная как приложение iondv для визуальной (no code) разработки приложений на IONDV. Framework. `Инструкция <https://github.com/iondv/nutrition-tickets/blob/master/tutorial/ru/index.md>`_ и `видео <https://www.youtube.com/watch?v=e201ko9fkQ8>`_ по созданию приложения с помощью IONDV. Studio. См. на `GitHub <https://github.com/iondv/studio>`_.
* `Telecom <https://telecom-ru.iondv.com>`_ - приложение по организации учета, хранения и отображения данных о наличии услуг связи
  (интернет, сотовая связь, телевидение, почта и др.) в населенных пукнтах региона. См. на `GitHub <https://github.com/iondv/telecom-ru>`_
* `DNT <https://dnt.iondv.com/>`_ - приложение для разработки и тестирования функциональности фреймворка, в котором каждая учетная сущность отражает тим метаданных, например класс "строка", или класс "коллекция". Это позволяет изучать возможности фреймворка через приложение. См. на `GitHub <github.com/iondv/develop-and-test>`_.
* `War Archive <https://war-archive.iondv.com/portal/index>`_ - это программное решение на основе IONDV. Framework, реализованное для действующего проекта "Вспомнить каждого", цель которого оцифровать архивные документы, внести информацию в базу и обеспечить к ним свободный доступ. См. на `GitHub <https://github.com/iondv/war-archive>`_.
* `Project Management <https://pm-gov-ru.iondv.com>`_ - приложение по  организации проектной деятельности региональных ОГВ , целью которой является контроль результатов, соблюдение и сокращение сроков их достижения, эффективное использование временных, человеческих и финансовых ресурсов, принятие своевременных и обоснованных управленческих решений. См. на `GitHub <https://github.com/iondv/pm-gov-ru>`_
* `CRM <https://crm-ru.iondv.com>`_ - это программное решение, реализованное для организации регистрации, учета, хранения и отображения бизнес-данных (входящие заявки, звонки, посетители, продукция, услуги). См. на `GitHub <https://github.com/iondv/crm-ru>`_

Логин для доступа - **demo**, пароль - **ion-demo**. 
Регистрация не требуется.

Типовые приложения
------------------

IONDV. Framework - конструктор веб-приложений широкой специфики, так как преметная область определяется структурой метаданных,
описывающих поведение приложение. Например, можно создать приложения:

* CRM - управление отношениями с клиентами;
* учет и управление ресурсами предприятия;
* автоматизация бизнес-процессов организации и документооборота;
* сбор и хранение любых данных, например метрик оборудования (IoT);
* представление данных в виде порталов;
* REST-API для SPA приложений;
* REST-API и бэкграунд для мобильных приложений;

Структура фреймворка
----------------------

Схема приложения на основе фреймворка: ``core + metadata + modules = application``


.. raw:: html

   <h1 align="center"> <a href="https://www.iondv.com/"><img src="https://raw.githubusercontent.com/iondv/docs-ru/master/_static/images/app_structure1.png" height="500px" alt="Application structure - core, metadata, modules" align="center"></a>
   </h1>


На рисунке отражены компоненты:

*  **ION Core** - это ядро приложения в виде IONDV. фреймворка;
*  **meta class**, **meta view**, **meta navigation**, **meta workflow**, **meta security** - это функциональные метаданные приложения - структуры, представления, навигации, бизнес-процессов и безопасности соответственно;
*  **registry module** - отражает подключаемые функциональные модули, например модуль registry для просмотра и редактирования данных;

Чуть ниже представлены дополнительные типы меты и модули. Они представляют собой дополнительную функциональность и применяются в соответствии со спецификой приложения. Зависимости приложения представлены в файле ``package.json``.

Приложение - это метаописание его поведения в файлах формата JSON (YAML) + функциональный код + HTML шаблоны,
расширяющие типовую функциональность -> с ним удобно работать через репозиторий версий git. Посмотрите примеры на `Github <https://github.com/search?q=org%3Aiondv+iondv-app&type=Repositories>`_ .

Подробнее о функциональных возможностях фреймворка IONDV. Framework и его модулей в `документации <https://iondv.readthedocs.io/ru/latest/key_features.html>`_.


Функциональные возможности
--------------------------

**IONDV. Framework** обеспечивает реализацию следующей функциональности:

* обеспечение трансляции описательных метаданных в структуру хранения данных в СУБД;
* обеспечение функциональности работы с различными СУБД (ORM технологию);
* обеспечение авторизации в системе с различными политиками, по умолчанию oath2, с открытым конфигурируемым API для подключения авторизационных модулей библиотеки passport обеспечивает до 500 различных политик авторизации;
* обеспечение безопасности доступа к данным – статической к типам данных, к навигации, к этапам бизнес-процессов, к действиям на форме; динамической – через условия в данных, которым должен соответствовать профиль текущего пользователя (принадлежность к подразделению или организации указанной в объекте, группе или другим условиям); через url; обеспечение исключения в авторизации и безопасности по url или для специального пользователя;
* подключение модулей, обеспечивающих дополнительную функциональность и реализуемую через доступ к интерфейсам (API) ядра;
* обеспечение импорта, экспорта данных в системе, метаданных, безопасности из файлов;
* обеспечение взаимодействия с файловой системой для хранения данных, в том числе с внешними файловыми хранилищами, такими как nextcloud;
* расчет значения с формулами и кэширование этих данных;
* обеспечение жадной загрузки данных и их фильтрации в связанных коллекциях;
* кэширование запросов и сессий в memcached, redis;
* выполнение задач по расписанию;
* уведомление пользователей по событиям.




Документация
------------

Документация по платформе IONDV.Framework доступна на двух языках  - `русский <https://iondv.readthedocs.io/ru/latest/index.html>`_ и `english <https://iondv.readthedocs.io/en/latest/index.html>`_.

Ссылки
------

Ссылки на дополнительную информацию по разработке приложений с использованием IONDV. Framework.

* `Документация <https://iondv.readthedocs.io/ru/latest/index.html>`_
* `Web-сайт <https://iondv.com/>`_
* Обучающие видеоролики на `Youtube <https://www.youtube.com/channel/UC_r2CGcOTfuV-7AXl6MwOqw>`_ 
* Обратная связь на `Facebook <https://www.facebook.com/iondv/>`_



----

`License <https://github.com/iondv/framework/blob/master/LICENSE>`_                              `Contact us <https://iondv.com/portal/contacts>`_                              `English <https://iondv.readthedocs.io/en/latest/index.html>`_
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Copyright (c) 2016-2020 **LLC "ION DV"**.
All rights reserved.

.. Indices and tables
.. ==================

.. c * :ref:`genindex`
.. c * :ref:`modindex`
.. c * :ref:`search`
