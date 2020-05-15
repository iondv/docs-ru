Прокси-клиент для доступа к функциям модуля без получения нового токена
-----------------------------------------------------------------------

Подключение клиента осуществляется в ``modules.registry.globals.di`` в ``deploy.json``\ :

.. code-block:: js

   {
     "modules": {
       "registry": {
         "globals": {
           "di":{
             "apiGateWay": {
               "module": "modules/rest/client/GateWay",
               "options": {
                 "log": "ion://sysLog",
                 "base": "/registry-ajax-api",
                 "clientId": "ext@system",
                 "clientSecret": "ion-demo",
                 "tokenPath": "/rest/token",
                 "endPoint": "[[rest.endPoint]]",
                 "definition": {
                   "paths": {
                     "/rest/echo-token": {
                       "post": true,
                       "get": true
                     }
                   }
                 }
               }
             }

Пример запроса к rest/echo-token через прокси-клиент:

.. code-block:: bash

   curl -X POST --cookie-jar 1.txt -d username="demo@local" -d password="ion-demo" http://localhost:8888/auth
   curl -X GET --cookie 1.txt https://dnt.iondv.com/registry-ajax-api/rest/echo-token

пример запроса в :doc:`dnt <../services/request_examples>`:
`test/modules/rest/gateway.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/gateway.spec.js>`_

.. code-block:: text

    /Checking rest-api proxy
