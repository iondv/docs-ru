
workflows PATCH
===============

Принудительное перемещение объекта в указанные состояния БП:

.. code-block:: text

   '/:class/:id', 'PATCH' 
   ["workflow1@namespace.state1", "workflow2@namespace.state2"]

Для метода **PATCH** передаем в теле запроса массив состояний разных БП. Последовательно помещаем обьект в каждое из переданных состояний.

Пример
------

Запрос (метод GET):

.. code-block:: bash

   curl -X GET -u demo@local:ion-demo http://dnt.iondv.com/rest/crud/workflowBase@develop-and-test/1

Ответ:

.. code-block:: js

   {
       "_id":"1",
       "__string":"1",
       "__class":"workflowBase@develop-and-test",
       "__classTitle":"Class of the WF object",
       "id":1,"stage":"checked",
       "stage_str":"Checked",
       "quantaty":12,
       "result":"Ready",
       "person":"admin@local",
       "creatorDefault":"admin@local"
   }
