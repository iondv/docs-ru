Ключевые функции ядра: dataRepo
===============================

//dataRepo
info from


#. core\impl\datarepository\ionDataRepository.js
#. core\interfaces\DataRepository\DataRepository.js
#. core\interfaces\MetaRepository\MetaRepository.js
#. core\impl\meta\DsMetaRepository.js
#. core\iterfaces\DataSource.js
#. 
   core\impl\datasource\mongodb.js
   //
   supported calls:

#. 
   wrap(className, data, [version], [options])
   supported options:
   user
   ...

#. 
   setValidators(validators[])
   ...

#. 
   getCount(obj, [options])
   supported options:
   filter

Возвращает количество объектов класса obj в базе данных.
...


#. getList(obj, [options])
   supported options:
   filter
   offset
   count
   sort
   countTotal
   nestingDepth
   env
   user

Возвращает список объектов класса obj в базе данных.
...


#. getIterator(obj, [options])
   supported options:
   filter
   offset
   count
   sort
   countTotal
   nestingDepth
   env
   user

предположительно https://docs.mongodb.com/manual/tutorial/iterate-a-cursor/
...


#. aggregate(className, [options])
   supported options:
   user
   expressions
   filter
   groupBy

предположительно https://docs.mongodb.com/manual/aggregation/

...



#. rawData(className, [options])
   supported options:
   user
   filter
   attributes
   distinct

https://docs.mongodb.com/manual/reference/method/db.collection.find/
...


#. 
   getItem(obj, [id], [options])
   supported options:
   filter
   nestingDepth
   user
   ...

#. 
   createItem(className, data, [version], [changeLogger], [options])
   supported options:
   nestingDepth
   skipResult
   adjustAutoInc
   user
   ...

#. 
   editItem(className, id, data, [changeLogger], [options])
   supported options:
   nestingDepth
   skipResult
   adjustAutoInc 
   user
   ...

#. 
   saveItem(className, id, data, [version], [changeLogger], [options])
   supported options:
   nestingDepth
   autoAssign
   skipResult
   adjustAutoInc
   user
   ...

#. 
   deleteItem(className, id, [changeLogger], [options])
   supported options:
   user
   ...

#. 
   put(master, collection, details, [changeLogger], [options])
   supported options:
   user
   ...

#. 
   eject(master, collection, details, [changeLogger], [options])
   supported options:
   user
   ...

#. 
   getAssociationsList(master, collection, [options])
   supported options:
   filter
   offset
   count
   sort
   countTotal
   nestingDepth
   user
   ...

#. 
   getAssociationsCount(master, collection, [options])
   supported options:
   filter
   offset
   count
   sort
   countTotal
   nestingDepth
   user
   ...

#. 
   bulkEdit(classname, data, [options])
   supported options:
   filter
   nestingDepth
   forceEnrichment
   user
   ...

#. 
   bulkDelete(classname, [options])
   supported options:
   filter
   user

#. 
   recache(item, [options])
   ...
