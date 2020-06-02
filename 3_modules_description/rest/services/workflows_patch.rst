
Перемещение объекта в указанное состояние бизнес-процесса: PATCH
================================================================

Методом **PATCH** осуществляется принудительное перемещение объекта в указанные состояния бизнес-процессов.
Запрос осуществляется по пути ``<URL сервера>/rest/<название сервиса>/<имя класса>/<id объекта>``. Имя класса указывается с неймспейсом.

В теле запроса передается массив целевых состояний бизнес-процессов, которые указываются как
строки в формате ``<имя бизнес-процесса>.<состояние>``. Имя бизнес-процесса указывается с неймспейсом.
Объект последовательно перемещается в каждое из состояний.

Пример запроса:

.. code-block:: js

    PATCH
    https://localhost:8888/rest/workflows/workflowBase@develop-and-test/1
    body: [
          'simpleWorkflow@develop-and-test.canStart'
        ]

В ответ будет возвращен список ошибок, возникших при перемещениях, либо пустой список.

Пример ``PATCH`` запроса к ``workflows`` в :doc:`dnt <request_examples>`:
`test/modules/rest/workflows.spec.js <https://github.com/iondv/develop-and-test/tree/master/test/modules/rest/workflows.spec.js>`_

.. code-block:: text

    /checking workflows service/# move the object to certain state in a workflow: PATCH
