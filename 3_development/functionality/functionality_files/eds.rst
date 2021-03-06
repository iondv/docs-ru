Электронно-цифровая подпись
===========================

Описание
--------

**Электронно-цифровая подпись (ЭЦП)** - это реквизит электронного документа, предназначенный для защиты данного электронного документа от подделки, полученный в результате криптографического преобразования информации с использованием закрытого ключа электронной цифровой подписи. Он позволяет идентифицировать владельца сертификата ключа подписи и установить отсутствие искажения информации в электронном документе.

Цель использования
------------------

В приложении ЭЦП может быть нужна для:


* Проверки целостности данных
* Определения авторства данных

Существует три вида электронной цифровой подписи, которые отличаются по своему применению:


* Простая электронно-цифровая подпись

  * для определения авторства данных
  * создается с использованием кодов, паролей или иных средств

* Усиленная неквалифицированная электронно-цифровая подпись

  * для проверки целостности данных
  * для определения авторства данных
  * создается с использованием средств электронной подписи

* Усиленная квалифицированная электронно-цифровая подпись

  * для проверки целостности данных
  * для определения авторства данных
  * для создания и проверки электронной подписи используются средства электронной подписи, получившие подтверждение соответствия требованиям законодательства

Специфика работы
----------------

Работает утилита ЭЦП на основе КриптоПро, поэтому он должен быть установлен на одном компьютере:


* ставим `крипто про <https://www.cryptopro.ru/products/csp/downloads>`_
* ставим `плагин <https://www.cryptopro.ru/products/cades/plugin>`_
* для тестирования, выпускаем `сертификат <https://www.cryptopro.ru/certsrv/certrqma.asp>`_

Реализация
----------

ЭЦП можно отнести к утилитам для приложения, так как основная ее реализация находится в приложении. Обычно реализация ЭЦП находиться в папке приложения ``lib/digest`` (на примере приложения project-management):


* ``lib/digest/digestData.js`` - проверка при загрузке формы объекта на необходимость в электронной подписи (_applicable) и процесс подписи при выполнении перехода БП (_process)
* ``lib/digest/signSaver.js`` - прикрепление подписи к объекту

Для того, чтобы статус ЭП запрашивался/отображался, для registry добавляем в ``deploy`` настройку signedClasses.

Пример
~~~~~~

.. code-block:: js

   "modules": {
       "registry": {
         "globals": {
            "signedClasses": [
             "class@application"
            ],
   ...

В БП ``workflows/indicatorValueBasic.wf.json`` добавляем переход со свойством ``"signBefore": true``.

Пример
~~~~~~

.. code-block:: js

    {
         "name": "needAppTrs_sign",
         "caption": "На утверждение",
         "startState": "edit",
         "finishState": "onapp",
         "signBefore": true,
         "signAfter": false,
         "roles": [],
         "assignments": [
           {
             "key": "state",
             "value": "onapp"
           }
         ],
         "conditions": []
       }

----
