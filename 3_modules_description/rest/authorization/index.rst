
Авторизация при запросах к сервисам
===================================

.. toctree::
    :titlesonly:
    :hidden:

    Получение токена <getting_token>
    Получение доступа через прокси-клиент <proxy_access>

Авторизация для доступа к сервисам может осуществляться следующими способами:

* `Без авторизации <#id5>`_
* `По учетной записи <#id6>`_
* `По токену <#id8>`_
* `Oauth2 <#id9>`_

Сервисы без аутентификации
--------------------------

Для реализации работы сервиса без аутентификации, необходимо задать для него значение ``none`` в настройке ``authMode`` в ``deploy.json``

.. code-block:: js

   {
     "modules": {
       "rest": {
         "globals": {
           "authMode": {
             "echo": "none"

Запрос к сервису не будет требовать аутентификации, пример запроса ``curl https://dnt.iondv.com/rest/echoo``

Пример запроса к сервису без аутентификации в :doc:`dnt <../services/request_examples>`:
`test/modules/rest/echo.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/echo.spec.js>`_

.. code-block:: text

    /Checking echo-pwd service/# Requesting echo-pwd GET/check if the request can be made using the headers auth


Сервисы со стандартрным механизмом авторизации по учетной записи
----------------------------------------------------------------

Все сервисы по умолчанию используют стандартный механизм авторизации, подразумевающий передачу учетных данных в заголовке:


* путем авторизации через Basic Auth, пример

  .. code-block:: bash

     curl -u demo@local:ion-demo https://dnt.iondv.com/rest/simple
пример запроса с авторизацией Basic Auth в :doc:`develop-and-test (dnt) <../services/request_examples>`:
`test/modules/rest/echopwd.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/echopwd.spec.js>`_

.. code-block:: text

    /Checking echo-pwd service/# Requesting echo-pwd GET/check if the request can be made using the basicAuth

* путем передачи учетных данных в заголовках запроса

  .. code-block:: bash

     curl -H "auth-user: demo" -H "auth-pwd: ion-demo" -H "auth-user-type: local" https://dnt.iondv.com/rest/simple

  или

  .. code-block:: bash

     curl -H "auth-user: demo@local" -H "auth-pwd: ion-demo" https://dnt.iondv.com/rest/simple

пример запроса с авторизацией учетными данными в заголовке в :doc:`dnt <../services/request_examples>`:
`test/modules/rest/echopwd.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/echopwd.spec.js>`_

.. code-block:: text

    /Checking echo-pwd service/# Requesting echo-pwd GET/check if the request can be made using the headers auth


Сервисы с аутентификацией через токен
-------------------------------------

Аутентификация по токену используется для исключения постоянной передачи учетной записи в запросах.
Токены ограничены по времени жизни.

Для реализации работы сервиса с аутентификацией через токен, необходимо задать для него значение ``token`` в настройке ``authMode`` в ``deploy.json``

.. code-block:: js

   {
     "modules": {
       "rest": {
         "globals": {
           "authMode": {
             "echo-token": "token"

Аутентификация через токен осуществляется путем отправки значения токена в заголовке запроса ``auth-token``

.. code-block:: bash

   curl -H "auth-token: c369a361db9742e9a9ae8e9fe55950a571493812" http://dnt.iondv.com/rest/echo-token

пример запроса с авторизацией через токен в :doc:`dnt <../services/request_examples>`:
`test/modules/rest/token.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/token.spec.js>`_

.. code-block:: text

    /Checking token service/# basicAuth authorization with admin rights/# check if the generated token is valid (basicAuth) (using echo-token)

подробнее о получении токена: :doc:`Получение токена <getting_token>`

Сервисы с аутентификацией методом OAuth2
----------------------------------------

Для реализации работы сервиса с аутентификацией oauth2, необходимо предварительно подключить в deploy.json плагин вида

.. code-block:: js

   "oauth": {
           "module": "lib/oAuthAdapter",
           "options": {
             "auth": "ion://auth",
             "dataSource": "ion://Db"
           }
         }

затем можно задать для сервиса значение ``oauth`` в настройке ``auth_mode``\ :

.. code-block:: js

   {
     "modules": {
       "rest": {
         "globals": {
           "authMode": {
             "echo-oauth": "oauth"

спецификация oauth2 доступна по ссылке: https://oauth2-server.readthedocs.io/en/latest/index.html

Этот тип авторизации используется для предоставления третьей стороне ограниченного доступа к ресурсам пользователя без необходимости предоставлять логин и пароль.
Запросы для получения доступа производятся в следующем порядке:


#.
   Со стороны пользователя получаем cookie с id сессии:

   .. code-block:: bash

      curl -X POST --cookie-jar 1.txt -d username="demo@local" -d password="ion-demo" http://dnt.iondv.com/auth

#.
   Используя авторизованную сессию разрешаем клиенту ext@system запросы от нашего имени:

   .. code-block:: bash

      curl -X POST --cookie ./1.txt "http://dnt.iondv.com/oauth2/grant?client_id=ext@system&response_type=code&state=123"

   В ответе будет содержаться параметр ``code``.

#.
   Теперь используя ``code`` можно получить токен:

   .. code-block:: bash

      curl -X POST -d grant_type="authorization_code" -d code="<code>" -H "Authorization:Basic ZXh0QHN5c3RlbTppb24tZGVtbw==" http://dnt.iondv.com/oauth2/token

   в заголовке Authorization нужно ввести ``Basic <client_secret>`` код клиента.
   В ответе будет получен ``access_token``.

#.
   Для запросов от лица пользователя в сервисах с авторизацией oauth2 теперь можно авторизоваться используя access_token:

   .. code-block:: bash

      curl -X POST -H "Authorization:Bearer <access_token>" http://dnt.iondv.com/rest/echo-oauth

пример запроса к сервису с авторизацией oauth2 в :doc:`dnt <../services/request_examples>`:
`test/modules/rest/echooauth.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/echooauth.spec.js>`_

.. code-block:: text

    /Checking echo-oauth service
