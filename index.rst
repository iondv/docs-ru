.. IONDV rest module documentation master file, created by
   sphinx-quickstart on Wed Dec 25 18:54:56 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Документация по платформе IONDV.Framework
=========================================

.. toctree::
   :caption: Содержание:
   :titlesonly:

   1_general/about
   2_getting_started/index
   3_development/index
   4_modules/modules
   key_features

5_ion_model_project/index

.. role:: raw-html-m2r(raw)
   :format: html



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


This page in `English <https://iondv.readthedocs.io/en/latest>`_


.. raw:: html

   <h1 align="center"> <a href="https://www.iondv.com/"><img src="https://raw.githubusercontent.com/iondv/docs-ru/master/_static/images/iondv_readme1.png" height="600px" alt="IONDV. Framework in numbers: rest api, soap, json, yaml, JavaScript - free open source web business application development" align="center"></a>
   </h1>


IONDV. Framework
----------------

Описание
~~~~~~~~

IONDV. Framework - это опенсорный фреймворк на node.js для разработки учетных приложений на основе метаданных в формате JSON/YAML
и отдельных функциональных модулей. Визуальный редактор `Studio <https://studio.iondv.com>`_ позволяет создавать приложения по
технологии "no code" и собирать приложение с веб-сервисами REST-API (модуль `rest <https://github.com/iondv/rest>`_).
Ключевой модуль `registry <https://github.com/iondv/registry>`_ является универсальным средством представления и
редактирования данных, обработки их по бизнес-процессам.

На видео технология разработки и сборки приложения.



.. raw:: html

   <iframe width="560" height="315" src="https://www.youtube.com/embed/s7q9_YXkeEo" frameborder="0" allowfullscreen></iframe>


Бесплатные демоверсии
~~~~~~~~~~~~~~~~~~~~~

Посмотрите наши демо уже сейчас:

* `Studio <https://studio.iondv.com/index>`_ - специализированная IDE созданная как приложение iondv, для визуальной (no code) разработки приложений на IONDV. Framework. `GitHub Репозиторий <https://github.com/iondv/studio>`_. `Видео инструкция <https://www.youtube.com/watch?v=e201ko9fkQ8>`_ и `текстовая <https://github.com/iondv/nutrition-tickets/blob/master/tutorial/ru/index.md>`_ по созданию приложения при помощи ION. Studio.
* `Telecom <https://telecom-ru.iondv.com>`_ - приложение по организации учета, хранения и отображения данных о наличии услуг связи
  (интернет, сотовая связь, телевидение, почта и др.) в населенных пукнтах региона. `GitHub Repo <https://github.com/iondv/telecom-ru>`_
* `DNT <https://dnt.iondv.com/>`_ - приложение для разработки и тестирования функциональности фреймворка, в котором каждая учетная сущность отражает тим метаданных, например класс "строка", или класс "коллекция". Это позволяет изучать возможности фреймворка через приложение. `GitHub Репозиторий <github.com/iondv/develop-and-test>`_.
* `War Archive <https://war-archive.iondv.com/portal/index>`_ - это программное решение на основе IONDV. Framework, реализованное для действующего проекта "Вспомнить каждого", цель которого оцифровать архивные документы, внести информацию в базу и обеспечить к ним свободный доступ. `GitHub Репозиторий <https://github.com/iondv/war-archive>`_.
* `Project Management <https://pm-gov-ru.iondv.com>`_ - приложение по  организации проектной деятельности региональных ОГВ , целью которой является контроль результатов, соблюдение и сокращение сроков их достижения, эффективное использование временных, человеческих и финансовых ресурсов, принятие своевременных и обоснованных управленческих решений. `GitHub Repo <https://github.com/iondv/pm-gov-ru>`_
* CRM - *скоро на GitHub*.

Логин для доступа - demo, пароль - ion-demo. Регистрация не требуется.

Типичные приложения
~~~~~~~~~~~~~~~~~~~

Фреймворк - конструктор веб-приложений любой специфики, так как преметная область определяется структурой метаданных,
описывающих поведение приложение. Например можно создать приложения

* CRM - управления отношения с клиентами;
* учет и управление ресурсов предприятия;
* автоматизация бизнес-процессов организации и документооборота;
* сбор и хранение любых данных, например метрик оборудования (IoT);
* представление данных в виде порталов;
* REST-API для SPA приложений;
* REST-API и бекграунд для мобильных приложений;

Функциональные возможности
~~~~~~~~~~~~~~~~~~~~~~~~~~

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


Структура фреймворка: ``core + metadata + modules = application``


.. raw:: html

   <h1 align="center"> <a href="https://www.iondv.com/"><img src="https://raw.githubusercontent.com/iondv/docs-ru/master/_static/images/app_structure1.png" height="500px" alt="Application structure - core, metadata, modules" align="center"></a>
   </h1>


На рискнуке:
- *ioncore* - ядро приложения в виде IONDV. фреймворка
- *meta class*, *meta view*, *meta navigation*, *meta workflow*, *meta security* - функциональные метаданные приложения - структуры, представления, навигации, бизнес-процессов и безопасности соответственно
- *registry module* - подлкючаемые функциональные модули, например модуль registry для просмотра и редактирования данных
Чуть ниже представлены дополнительные типы меты и модули. Они представляют собой дополнительную функциональность и применяются в соответствии с приложением. Зависимости приложения смотрим в файле ``package.json``.

Так как приложение - это метаописание его поведения в файлах формата JSON (YAML) и функциональный код и HTML шаблоны
расширяющие типовую функциональность - то с ним удобно работать через репозиторий версий git. Посмотрите примеры на `Github <https://github.com/search?q=org%3Aiondv+iondv-app&type=Repositories>`_

Подробнее о функциональных возможностях фреймворка и его модулей можно узнать :doc:`в документации <key_features>`.

Быстрый старт
~~~~~~~~~~~~~

Вы можете посмотреть собранные приложения, развернутые в облаке или получить продукты для изучения другим способом на `сайте фреймворка <https://iondv.com>`_\ , в том числе:

* инсталятор для операционной системы `Linux <https://github.com/iondv/iondv-app>`_
* клонирование репозитория приложения и установка всех компонентов (инструкция ниже)
* `docker-контейнеры <https://hub.docker.com/u/iondv>`_ с собранными приложениями

Cистемное окружение
~~~~~~~~~~~~~~~~~~~

Запуск фреймворка осуществляется в среде `Node.js <https://nodejs.org/en/>`_ версии 10.x.x.

Для хранения данных необходимо установить и запустить `MongoDb <https://www.mongodb.org/>`_ версии старше 3.6.

Установщик
~~~~~~~~~~

Для ускорения Вы можете использовать установщик приложений IONDV. Framework `iondv-app <https://github.com/iondv/iondv-app>`_\ , требующий установленных node, mongodb и git.
В ходе установки будет проверены и установлены все остальные зависимости, а также собрано и запущено само приложение.

Установка в одну строку:

.. code-block:: bash

   bash <(curl -sL https://raw.githubusercontent.com/iondv/iondv-app/master/iondv-app) -t git -q -i -m localhost:27017 develop-and-test

Где параметры для iondv-app ``localhost:27017`` адрес MongoDB, а ``develop-and-test`` название приложения. После запуска открыть ссылку 'http://localhost:8888', типовая учетная запись бек офиса **demo**\ , пароль **ion-demo**.

Дугой способ заключается в клонировании сборщика - (\ ``git clone https://github.com/iondv/iondv-app.git``\ ) и установите приложение с помощью команды ``bash iondv-app -m localhost:27017 develop-and-test``.

Можно также собрать приложение в докер конейтнерах, тогда из окружения нужен только docker и СУБД mongodb в докер контейнере. Подробнее на странице сборщика приложения  IONDV. Framework `iondv-app <https://github.com/iondv/iondv-app>`_

Сборка приложения из репозитория
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Глобальные зависимости
^^^^^^^^^^^^^^^^^^^^^^

Для сборки компонентов и библиотек фреймворка необходимо установить глобально:

* пакет `node-gyp <https://github.com/nodejs/node-gyp>`_ ``npm install -g node-gyp``. Для работы библиотеки под операционной системой семейства windows дополнительно необходимо установить пакет windows-build-tools ``npm install -g --production windows-build-tools``.
* пакет сборщика проектов `Gulp <http://gulpjs.com/>`_ ``npm install -g gulp@4.0``. ``4.0`` - поддерживаемая версия ``Gulp``.
* для версий IONDV. Framework 3.x.x и более ранних нужен менджер пакетов фронтенд библиотек `Bower <https://bower.io>`_ ``npm install -g bower``. Для версия 4.х.х и старше не требуется.

Ручная установка ядра, модулей и приложения
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Рассматриваем на примере приложения ``develop-and-test``. Находим приложение ``develop-and-test`` в репозитории.
Смотрим зависимости указаные в файле ``package.json``.

.. code-block:: js

   "engines": {
    "ion": "1.24.1"
  },
  "ionModulesDependencies": {
    "registry": "1.27.1",
    "geomap": "1.5.0",
    "graph": "1.3.2",
    "portal": "1.3.0",
    "report": "1.9.2",
    "ionadmin": "1.4.0",
    "dashboard": "1.1.0",
    "lk": "1.0.1",
    "soap": "1.1.2",
    "gantt-chart": "0.8.0"
  },
  "ionMetaDependencies": {
    "viewlib": "0.9.1"
    "viewlib-extra": "0.1.0"

* Начинаем установку с ядра, версия которого указана в парметре ``"engines": {"ion": "1.24.1"}``. Скопируйте адрес репозитория ядра и в командной строке выполните комманду ``git clone https://github.com/iondv/framework``. Перейдите в папку ядра, переключитесь на tag номера версии ``git checkout tags/v1.24.1``.  Так как совместимость обеспечивается на уровне метаданных, а новые версии выпускались из-за изменения технологии сборки, то вы можете использовать последнии, например 4.0.0.
* После этого устанавливаются необходимые для приложения модули, указанные в параметре ``"ionModulesDependencies"``. Модули устанавливаются в папку ``modules`` ядра, для этого перейдите в неё командой ``cd modules``. Клонируем модули из списка ``"ionModulesDependencies"``, для модуля registry это осуществляется коммандой ``git clone https://github.com/iondv/registry``. Перейдите в папку установленного модуля, переключитесь на tag номера версии ``git checkout tags/v1.27.1``. Повторите для каждого модуля. Для большинства приложений, можно использовать последние совместимые с ядром модули.
* Установка самого приложения осуществляется в папку ``applications``, для этого перейдите в неё командой  ``cd ..\applications``, если вы находитесь в папке модулей. Установку выполните клонированием репозитория коммандой ``git clone https://github.com/iondv/dnt_ru``.
* После этого установите дополнительно необходимые приложения из параметра ``"ionMetaDependencies"``. Установка осуществляется в папку ``applications``, для установки необходимо убедиться, что находитесь в папке приложений. Клонируем приложения из списка в параметре  ``"ionMetaDependencies"``, для приложения ``viewlib`` осуществляется командой ``https://github.com/iondv/viewlib``.  Перейдите в папку установленного приложения, переключитесь на tag номера версии ``git checkout tags/v0.9.1``. Повторите для каждого приложения.

Сборка, конфигурирование и развертывание приложения
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Сборка приложения обеспечивает установку всех зависимых библиотек, импорт данных в базу данных и подготовку приложения для запуска.

Создайте конфигурационный файл ``setup.ini``  в папке ``config`` куда вы клонировали фреймворк для задания основных параметров окружения приложения.

.. code-block:: ini

   auth.denyTop=false
   auth.registration=false
   db.uri=mongodb://127.0.0.1:27017/db
   server.ports[]=8888
   module.default=registry
   fs.storageRoot=./files
   fs.urlBase=/files

Открываем файл в редакторе и вставляем содержимое. Самый главный параметр ``db.uri=mongodb://127.0.0.1:27017/ion-dnt`` он указывает на название базы которую мы будем использовать для приложения. База данных будет создана автоматически.

Задайте переменную окружения NODE_PATH равной пути к ядру приложения следующей командой ``set NODE_PATH=c:\workspace\dnt`` для Windows и ``export NODE_PATH=/workspace/dnt`` для Linux, где ``workspace\dnt`` - папка куда склонирован фреймворк.

При первом запуске необходимо выполнить ``npm install`` - она поставит ключевые зависимости, в том числе локально сборщик ``gulp``.

Далее выполните команду сборки приложения ``gulp assemble``.

Если вы хотите выполнить импорт данных в вашем проекте, проверьте папку ``data`` в приложении и выполните команду:
``node bin/import-data --src ./applications/develop-and-test/data --ns develop-and-test``

Добавьте пользователя admin с паролем 123 командой ``node bin\adduser.js --name admin --pwd 123``.

Добавьте пользователю права администратора командой ``node bin/acl.js --u admin@local --role admin --p full``.

Запуск
^^^^^^

Запустите приложение командой в папке ядра ``npm start`` или ``node bin\www``.

Откройте браузер с адресом ``http://localhost:8888`` и авторизуйтесь в приложении, где ``8888`` - порт указанный в параметре server.ports конфигурации запуска.

Docker
~~~~~~

Запуск приложения с использованием докер контейнера:


#. Запустите СУБД mongodb: ``docker run --name mongodb -v mongodb_data:/data/db -p 27017:27017 -d mongo``
#. Запустите IONDV. develop-and-test  ``docker run -d -p 80:8888 --link mongodb iondv/develop-and-test``.
#. Откройте ссылку ``http://localhost`` в браузере через минуту (время требуется для инициализации данных). Для авторизации используйте типовой логин: **demo**\ , пароль: **ion-demo**

Документация
------------

Документация по платформе IONDV.Framework доступна на двух языках  - `русский <https://iondv.readthedocs.io/ru/latest/index.html>`_ и `english <https://iondv.readthedocs.io/en/latest/index.html>`_.

Ссылки
------

Ниже представлены ссылки на дополнительную информацию по разработке приложений с использованием IONDV.Framework.

* `Документация <https://iondv.readthedocs.io/ru/latest/index.html>`_
* `Домашняя страница фреймворка <https://iondv.com/>`_
* Обратная связь на `Facebook <https://www.facebook.com/iondv/>`_
* Обучающие видеоролики на `youtube <https://www.youtube.com/channel/UC_r2CGcOTfuV-7AXl6MwOqw>`_


----

`License <https://github.com/iondv/framework/blob/master/LICENSE>`_                              `Contact us <https://iondv.com/portal/contacts>`_                              `English <https://iondv.readthedocs.io/en/latest/index.html>`_
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Copyright (c) 2016-2020 **LLC "ION DV"**.\ :raw-html-m2r:`<br>`
All rights reserved.

.. Indices and tables
.. ==================

.. c * :ref:`genindex`
.. c * :ref:`modindex`
.. c * :ref:`search`
