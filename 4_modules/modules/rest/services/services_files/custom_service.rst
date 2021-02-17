Разработка обработчика сервиса в приложении
===========================================

Все сервисы реализуются как наследники от Service - функции модуля rest.

Каждый сервис должен экспортировать функцию обработчика, в которой реализован асинхронный метод ``this._route``\ , в котором
необходимо зарегистрировать обрабатываемые методы и пути через функции ``this.addHandler``, возвращающие Promise. Функция обработки
будет иметь доступ к ``options``\ , через который доступ к репозиториям данных, авторизации, метаданным и классам (если они
указаны в конфигурации приложения в файле deploy.json), а также получит объект с типовым названием ``req`` - являющимся
объектом ``request`` библиотеки `express <https://expressjs.com/en/4x/api.html#req>`_.
Данные, прошедшие парсинг в объект будут находиться в ``req.body``.

Функция-обработчик должна вернуть Promise разрешающийся в результат обработки (для обработки в Service ``modules/rest/lib/interfaces/Service.js``\ ),
обработчик выдаст его с кодом ``200`` и типом содержания ``Content-Type:application/json``.
Если в ходе обработки будет ошибка, перехваченная catch, то для ошибок связанных с контролем доступа будет возвращен ответ с текстом ошибки и с кодом ``403``\ , а для всех остальных код ответа ``500`` и сообщением об ошибке ``Internal server error``.

Заголовок можно переопределить, для этого в ответе нужно отдать тип заголовка ``headers``\ , а объект в атрибуте ``data``

.. code-block:: js

   Promise.resolve({headers: ['Content-Type: image/png', 'Content-Length: 107'],
     data: Buffer.from([0x89, 0x50, 0x4E, 0x47, 0x0D, 0x0A, 0x1A, 0x0A, 0x00, 0x00, 0x00, 0x0D, 0x49,
             0x48, 0x44, 0x52, 0x00, 0x00, 0x00, 0x01, 0x00, 0x00, 0x00, 0x01, 0x08, 0x06, 0x00, 0x00, 0x00,
             0x1F, 0x15, 0xC4, 0x89, 0x00, 0x00, 0x00, 0x06, 0x62, 0x4B, 0x47, 0x44, 0x00, 0xFF, 0x00, 0xFF,
             0x00, 0xFF, 0xA0, 0xBD, 0xA7, 0x93, 0x00, 0x00, 0x00, 0x09, 0x70, 0x48, 0x59, 0x73, 0x00, 0x00,
             0x2E, 0x23, 0x00, 0x00, 0x2E, 0x23, 0x01, 0x78, 0xA5, 0x3F, 0x76, 0x00, 0x00, 0x00, 0x0B, 0x49,
             0x44, 0x41, 0x54, 0x08, 0xD7, 0x63, 0x60, 0x00, 0x02, 0x00, 0x00, 0x05, 0x00, 0x01, 0xE2, 0x26,
             0x05, 0x9B, 0x00, 0x00, 0x00, 0x00, 0x49, 0x45, 0x4E, 0x44, 0xAE, 0x42, 0x60, 0x82])
   })

Пример реализации сервиса, выдающего списки объектов с фильтрами для класса ``class_string`` есть в приложении ``develop-and-test``.
Также, для изучения удобно смотреть сам метод crud, находящийся по адресу ``modules/rest/lib/impl/crud.js``

.. code-block:: js

   const Service = require('modules/rest/lib/interfaces/Service');

   /**
    * @param {{dataRepo: DataRepository, echoClassName: String}} options
    * @constructor
    */
   function listClassString(options) {

     /**
      * @param {Request} req
      * @returns {Promise}
      * @private
      */
     this._route = function(router) {
       this.addHandler(router, '/', 'POST', (req) => {
         return new Promise(function (resolve, reject) {
           try {
             let filter = [];
             if (req.body.string_text)
               filter.push({string_text: {$eq: req.body.string_text}});
             if (req.body.string_miltilinetext)
               filter.push({string_miltilinetext: {$eq: req.body.string_miltilinetext}});
             if (filter.length === 0)
               filter = {};
             else if (filter.length === 1)
               filter = filter[0];
              else
               filter = {$and: filter};
             options.dataRepo.getList(options.stringClassName, {filter: filter}).then(function (results) {
               let items = [];
               for (let i = 0; i < results.length; i++) {
                 const props = results[i].getProperties();
                 const item = {};
                 for (let p in props) {
                   if (props.hasOwnProperty(p))
                     item[props[p].getName()] = props[p].getValue();
                 }
                 items.push(item);
               }
               resolve({data: items});
             });
           } catch (err) {
             reject(err);
           }
         });
       });
     }
   }

   listClassString.prototype = new Service();

   module.exports = listClassString;

Запрос без атрибутов в теле запроса

.. code-block:: bash

   curl -X POST -u demo@local:ion-demo https://dnt.iondv.com:8888/rest/string-list

вернет весь список:

.. code-block:: js

   [{"__class":"class_string@develop-and-test",
     "__classTitle":"Class \"String [0]\"",
     "id":"4567a830-b8ea-11e9-9cdf-7bd384cbb7a5",
     "string_text":"example1",
     "string_miltilinetext":"example1",
     "string_formattext":"<p>example1</p>"},
   {"__class":"class_string@develop-and-test",
     "__classTitle":"Class \"String [0]\"",
     "id":"4a80bdc0-b8ea-11e9-9cdf-7bd384cbb7a5",
     "string_text":"example1",
     "string_miltilinetext":"example2",
     "string_formattext":"<p>example2</p>"},
   {"__class":"class_string@develop-and-test",
     "__classTitle":"Class \"String [0]\"",
     "id":"66dbb3d0-5583-11e6-aef7-cf50314f026b",
     "string_text":"Example of the \"String [0]\" type in the \"Text [1]\" view",
     "string_miltilinetext":"Example of the \"String [0]\"\r\n in the Multiline text [7] view",
     "string_formattext":"Example of the \r\n \"String [0]\" type \r\n in the \r\nFormatted text [7] view"}]

А запрос с параметром атрибута равного значению в атрибуте string_text
``Example of the \"String [0]\" type in the \"Text [1]\" view``

.. code-block:: bash

   curl -X POST -d "string_text=Example of the \"String [0]\" type in the \"Text [1]\"" \
        -u demo@local:ion-demo https://dnt.iondv.com:8888/rest/string-list

вернет объекты удовлетворяющие условию:

.. code-block:: js

   [{"__class":"class_string@develop-and-test",
     "__classTitle":"Class \"String [0]\"",
     "id":"66dbb3d0-5583-11e6-aef7-cf50314f026b",
     "string_text":"Example of the \"String [0]\" type in the \"Text [1]\" view",
     "string_miltilinetext":"Example of the \"String [0]\"\r\n in the Multiline text [7] view",
     "string_formattext":"Example of the \r\n \"String [0]\" type \r\n in the \r\nFormatted text [7] view"}]

Пример регистрации тестового сервиса, подробнее см. `Регистрация сервиса в конфигурации приложения <service_configuration.rst>`_

.. code-block:: js

   {
     "modules": {
       "rest": {
         "globals": {
           "di": {
             "string-list": {
               "module": "applications/develop-and-test/service/String-list",
               "options": {
                 "stringClassName": "class_string@develop-and-test",
                 "dataRepo": "ion://dataRepo"
               }
             }

Для реализации обработки multipart запросов, например для запросов, содержащих файлы, можно использовать библиотеку ``multipart.js`` (``rest/backend/multipart.js``) модуля ``REST``. Пример реализации есть в сервисе ``CRUD``:

.. code-block:: js

    function reqToData(req) {
        return multipart(req).then(data => data || req.body);
    }

Этой цели также служит библиотека ``util.js`` (``rest/backend/util.js``), обеспечивающая корректность действий при работе с файлами и файловым хранилищем, пример из ``CRUD``:

.. code-block:: js

    reqToData(req)
      .then(data => <util.js.>prepareUpdates(options, data, cm, req.params.id))
