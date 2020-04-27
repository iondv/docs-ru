
Встроенный сервис "token"
=========================

Сервис ``token`` предназначен для выдачи токена пользователю, прошедшему аутентификацию, для его дальнейшего использования в сервисах
осуществляющих аутентификацию по токену.

Сервис не требует регистрации в deploy.json. Сервис обеспечивает выдачу токена для авторизованного пользователя,
если он имеет права ``use`` для ресурса ``ws:::gen-ws-token``  или имеет права администратора. В ответ на запрос, возвращается
токен вида ``e444c69894d2087696e0a6c6914788f67ebcf6ee``. Время жизни токена по умолчанию 100 лет.

Пример запроса через аутентификацию типа Basic Auth

.. code-block:: bash

   curl -u demo@local:ion-demo https://dnt.iondv.com/rest/token

Пример запроса  с аутентификацией через параметры в заголовке

.. code-block:: bash

   curl -H "auth-user: demo@local" -H "auth-pwd: ion-demo" -H "auth-user-type: local" https://dnt.iondv.com/rest/token

dnt: `test/modules/rest/token.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/token.spec.js>`_

.. code-block:: text

    /Checking token service/# basicAuth authorization with admin rights
    /Checking token service/# authorization with admin rights using header parameters
