# Creating a Multikey Index in MongoDB

When we define an index on an array field, that index is called a multikey index. 

Multikey indexes can index primitives, sub-documents, or sub-arrays. 

We can have an array field in a single field index or in the compound index. 

~~~js
db.customers.createIndex({ accounts: 1 });
~~~

~~~js
db.customers.createIndex({ email: 1, accounts: 1 });
~~~

For instance, these two commands will create multi-key indexes because they include the field accounts, which is an array. 

There is a limitation of only one array field per index. If an index has multiple fields, only one of them can be an array. Internally, MongoDB decomposes the array and stores each unique value found within it as an individual index entry. 

