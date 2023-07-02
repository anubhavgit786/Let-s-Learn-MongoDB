# **Creating a Single Field Index in MongoDB**

Single field indexes are indexes on single field. They support queries and sort on single field. 

~~~js
db.<collection>.createIndex({ <field>: <value>});
~~~

<value> is 1 for ascending order and -1 for descending order. 

~~~js
db.customers.createIndex({
  birthdate: 1
})
~~~

## **Create a Unique Single Field Index**

Add ```{unique:true}``` as a second, optional, parameter in createIndex() to force uniqueness in the index field values. Once the unique index is created, any inserts or updates including duplicated values in the collection for the index field/s will fail.    

~~~js
db.customers.createIndex({
  email: 1
},
{
  unique:true
})
~~~

## **View the Indexes used in a Collection**

Use ```getIndexes()``` to see all the indexes created in a collection.

~~~js
db.customers.getIndexes()
~~~

## **Check if an index is being used on a query**

Use explain() in a collection when running a query to see the Execution plan. This plan provides the details of the execution stages (IXSCAN , COLLSCAN, FETCH, SORT, etc.).

* The IXSCAN stage indicates the query is using an index and what index is being selected.

* The COLLSCAN stage indicates a collection scan is perform, not using any indexes.

* The FETCH stage indicates documents are being read from the collection.

* The SORT stage indicates documents are being sorted in memory.

~~~js
db.customers.explain().find({
  birthdate: {
    $gt:ISODate("1995-08-01")
    }
})
db.customers.explain().find({
  birthdate: {
    $gt:ISODate("1995-08-01")
    }
  }).sort({
    email:1
})
~~~

