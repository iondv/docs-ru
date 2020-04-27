
Регистрация сервиса в конфигурации приложения
---------------------------------------------

Для подключения сервисов в приложении их необходимо сконфигурировать в глобальных настройках модуля rest в файле
deploy.json приложения. Пример приведен ниже.

.. code-block:: js

   {
     "modules": {
       "rest": {
         "globals": {
           "di": {
             "simple": {
               "module": "applications/develop-and-test/service/SimpleRest"
             },
             "string-list": {
               "module": "applications/develop-and-test/service/String-list",
               "options": {
                 "stringClassName": "class_string@develop-and-test",
                 "dataRepo": "ion://dataRepo"
               }
             },
             "crud": {
               "module": "modules/rest/lib/impl/crud",
               "options": {
                  "auth": "ion://auth",
                  "dataRepo": "ion://securedDataRepo"
               }
             }

Путь к регистрациям сервиса в файле ``deploy.json`` - ``modules.rest.globals.di``\ , далее указывается название сервиса, которое
будет доступно по адресу ``https://domain.com/rest/serviceName``\ , где serviceName - имя сервиса, указываемого в di, например
в примере выше ``simple`` или ``string-list``. В атрибуте ``module`` указывается путь к js-файлу с обработчиком сервиса с путем относительно
корня фреймворка. Обработчик может быть как в приложении, так и в любом модуле или фреймворке, в т.ч. типовые обработчики модуля rest.

В параметре ``options`` указываются специфические настройки сервиса.
Например, для сервиса **crud** указаны:


* в поле ``dataRepo`` - репозиторий данных с контролем доступа, используемый для операций над обьектами
* в поле ``auth``\ - компонент аутентификации, используемый для получения текущей учетной записи пользователя.
  А для сервиса **string-list** указаны:
* в поле ``dataRepo`` - репозиторий данных, используемый для выборки данных
* в поле ``stringClassName`` - имя класса получаемых обьектов
  в данном случае класс ``class_string@develop-and-test`` будет передан в метод ``getList`` репозитория данных

  .. code-block:: javascript

     options.dataRepo.getList(options.stringClassName, {})