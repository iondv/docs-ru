
Выполнение перехода объекта по бизнес-процессу: PUT
===================================================

Методом **PUT** сервиса ``workflows`` осуществляется выполнение переходов объекта по БП (в том числе последовательных).
Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/<имя класса>/<id объекта>``.

Имя класса указывается с неймспейсом.

В теле запроса передается один из вариантов:

* объект с атрибутами - именами БП, которые содержат список из переходов по этим бизнес-процессам.
* список из строк формата ``<имя бизнес-процесса>.<название перехода>

имена бизнес-процессов указываются с неймспейсом.

Пример запроса:

.. code-block:: text

    PUT
    https://localhost:8888/rest/workflows/workflowBase@develop-and-test/1
    body: {
          'simpleWorkflow@develop-and-test': [
            'startCheck',
            'accept'
          ]
        }

что равносильно:

.. code-block:: text

    PUT
    https://localhost:8888/rest/workflows/workflowBase@develop-and-test/1
    body: [
        'simpleWorkflow@develop-and-test.startCheck',
        'simpleWorkflow@develop-and-test.accept'
    ]

Переходы выполняются последовательно. Для каждого перехода будет предпринята попытка выполнения, даже если в одном из них произошла ошибка.

В ответ будет возвращен список из ошибок по каждому переходу:

.. code-block:: js

    [ { code: 'workflow.ti',
        params: { workflow: 'Simple WF', trans: 'Start checking' },
        message:
         'Невозможно выполнение перехода \'Start checking\' рабочего процесса \'Simple WF\'.' },
    { code: 'workflow.ti',
        params: { workflow: 'Simple WF', trans: 'Accept' },
        message:
         'Невозможно выполнение перехода \'Accept\' рабочего процесса \'Simple WF\'.' } ]

или пустой список.

Примеры ``PUT`` запросов к ``workflows`` в :doc:`dnt <request_examples>`:
`test/modules/rest/workflows.spec.js <https://github.com/iondv/develop-and-test/test/modules/rest/workflows.spec.js>`_

.. code-block:: text

    /checking workflows service/# move the object through workflow: PUT, list body
    /checking workflows service/# move the object through workflow: PUT, object body
