Операции с учетными записями MongoDB через CLI
==============================================

Авторизация
-----------

Для авторизации при взаимодействии с СУБД через консольный интерфейс, в ``mongo`` передаются параметры

1. ``--authenticationDatabase <база данных, на основе которой производится авторизация>``
2. ``-u <имя пользователя>``
3. ``-p <пароль>``

пример:

.. code-block:: text

    mongo --authenticationDatabase admin -u admin -p 123

Создание пользователя
---------------------

Для создания пользователя необходимо иметь роль ``dbOwner``, либо иметь роль ``userAdmin`` в базе данных, на основании которой производится авторизация,
например ``admin``, и во всех базах данных, где добавляются роли, или привилегию на действие ``createUser`` в этой базе и привилегии на действие ``grantRole`` в базах данных, где добавляются роли.

Создание пользователя через консольный интерфейс осуществляется командой

.. code-block:: sh

    mongo --eval "(new Mongo()).getDB(<имя бд, куда писать данные авторизации>').createUser( \
    { \
      user: '<пользователь>', \
      pwd: '<пароль>', \
      roles: [ \
        { role: 'readWrite', db: '<бд куда доступ на чтение-запись>' }, \
        { role: 'read', db: '<бд где только чтение>' }, \
        { role: 'write', db: '<бд где только запись>' } \
      ]})"

пример:

.. code-block:: sh

    mongo --eval "(new Mongo()).getDB('admin').createUser( \
    { \
      user: 'admin', \
      pwd: '123', \
      roles: [ \
        { role: 'readWrite', db: 'admin' }, \
        { role: 'readWrite', db: 'config' }, \
        { role: 'readWrite', db: 'local' } \
      ]})"

или в одну строку

.. code-block:: sh

    mongo --eval "(new Mongo()).getDB('admin').createUser({user: 'demo',pwd: '123',roles: [{ role: 'readWrite', db: 'admin' },{ role: 'readWrite', db: 'config' },{ role: 'readWrite', db: 'local' }]})"

Удаление пользователя
---------------------

Для удаления пользователя необходимо иметь роль ``dbOwner``, либо иметь роль ``userAdmin`` или привилегию на действие ``dropUser`` в базе данных, на основе которой производится
авторизация, например ``admin``.

Удалить пользователя через CLI mongodb можно командой

.. code-block:: sh

    mongo --eval "(new Mongo()).getDB('<бд с данными авторизации>').dropUser('<имя>')"

пример:

.. code-block:: sh

    mongo --eval "(new Mongo()).getDB('admin').dropUser('demo')"
