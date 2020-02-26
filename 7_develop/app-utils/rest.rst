.. role:: raw-html-m2r(raw)
   :format: html


Утилиты для веб-сервиса (rest)
==============================

Назад: `Функциональные утилиты приложения <./readme.md>`_  

Утилиты веб-сервиса предназначены для реализации обработки различных видов запросов к серверу.\ :raw-html-m2r:`<br>`
Cервис подключается к приложению в deploy.json в объекте modules.rest.globals.di, например так:

.. code-block::

   {
     "modules": {
       "rest": {
         "globals": {
           "di": {
             "acceptor": {
               "module": "modules/rest/lib/impl/acceptor",
               "options": {
                 "dataRepo": "ion://dataRepo",
                 "metaRepo": "ion://metaRepo"
   ...

В этом случае подключается сервис ``acceptor``\ , он станет доступен для запросов по url ``https://dnt.iondv.com/rest/acceptor``.\ :raw-html-m2r:`<br>`
Функциональное описание взаимодействия с запросами должно содержаться в скрипте ``modules/rest/lib/impl/acceptor.js``.\ :raw-html-m2r:`<br>`
В поле ``options`` могут быть указаны любые переменные и их значения, которые станут доступны в скрипте через поля объекта, передаваемого как аргумент основной функции модуля.

Скрипт составляется в формате модуля, например так:

.. code-block::

   const Service = require('modules/rest/lib/interfaces/Service');

   /** Simple app service - REST module
    * @param {{dataRepo: DataRepository, metaRepo: MetaRepository}} options
    * @constructor
    */
   function EchoRest(options) {
     this._route = function(router) {
       this.addHandler(router, '/', 'POST', (req) => {
         return Promise.resolve({
           echo: 'peekaboo'
         });
       });
       this.addHandler(router, '/', 'GET', (req) => {
         return Promise.resolve({
           echo: 'peekaboo'
         });
       });
     };
   }
   EchoRest.prototype = new Service();
   module.exports = EchoRest;

Подробное описание принципов создания сервиса можно найти в https://github.com/iondv/rest/blob/master/README_RU.md ``#### Разработка обработчика сервиса в приложении``
