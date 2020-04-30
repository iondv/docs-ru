
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

примеры запросов к сервису token в :doc:`dnt <request_examples>`:
`test/modules/rest/token.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/token.spec.js>`_

.. code-block:: text

    /Checking token service/# basicAuth authorization with admin rights
    /Checking token service/# authorization with admin rights using header parameters

Добавить ресурс возможности генерации токенов для роли, можно из комадной строки ``node bin/acl.js --role restGrp --p USE --res ws:::gen-ws-token``
(где restGrp название существующей группы)

Второй способ добавления прав на ресурс - использование консоли администратора модуля ionadmin, например, перейдя по адресу ``locahost:8888/ionadmin/``:

* Выберите пункт навигации "Безопасность",
* Выберите подпункт навигации "Роли"
* Выберите существующую роль и нажмите кнопку редактировать или создать новую роль.
* В поле "Права доступа" роли выберите вкладку "Services"
* Раскройте список прав для ресурса "Генерация токенов безопасности посредством веб-сервисов (ws:::gen-ws-token)"
* Выбрать пункт "Использование" и нажмите кнопку "Сохранить"