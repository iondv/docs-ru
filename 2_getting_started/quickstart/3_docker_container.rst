Docker
======

Запуск приложения с использованием докер контейнера:


#. Запустите СУБД mongodb: ``docker run --name mongodb -v mongodb_data:/data/db -p 27017:27017 -d mongo``
#. Запустите IONDV. develop-and-test  ``docker run -d -p 80:8888 --link mongodb iondv/develop-and-test``.
#. Откройте ссылку ``http://localhost`` в браузере через минуту (время требуется для инициализации данных). Для авторизации используйте типовой логин: **demo**\ , пароль: **ion-demo**
