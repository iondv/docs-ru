Ключевые поля
=============

В каждом классе обязательно должен быть задан ключевой атрибут (поле ``"key"`` основной части меты класса). Без этого приложение не будет функционировать.

Типы ключевых полей
-------------------


#. Guid - "Глобальный идентификатор [12]". 
#. "Строка [0]". 
#. "Целое [6]". 

Требования к ключевому атрибуту
-------------------------------

При формировании меты ключевого атрибута,  поля ``"unique"`` и  ``"autoassigned"``  выставляются в ``true``. Необходимо запретить пустое значение, выставляя  ``"nullable"`` в ``false``.

Если атрибут не генерируется автоматически, то ``"autoassigned"`` можно поставить в ``false``\ , тогда поле должно быть задано оператором при создании. Например, если это код классификатора или регистрационный номер задаваемый внешним способом (на бумаге).  


----
 
