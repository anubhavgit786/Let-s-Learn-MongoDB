# **Deleting MongoDB Indexes**

## **Delete an Index**
Use ```dropIndex()``` to delete an existing index from a collection. Within the parentheses of ```dropIndex()```, include an object representing the index key or provide the index name as a string.

### **Delete index by name:**

~~~js
db.customers.dropIndex('active_1_birthdate_-1_name_1');
~~~

### **Delete index by key:**

~~~js
db.customers.dropIndex({
  active:1,
  birthdate:-1, 
  name:1
})
~~~

## **Delete Indexes**

Use **```dropIndexes()```**  to delete all the indexes from a collection, with the exception of the default index on ```_id```.

~~~js
db.customers.dropIndexes()
~~~

The dropIndexes() command also can accept an array of index names as a parameter to delete a specific list of indexes.

~~~js
db.collection.dropIndexes([
  'index1name', 'index2name', 'index3name'
])
~~~



