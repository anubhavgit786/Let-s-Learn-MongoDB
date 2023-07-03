# **Updating MongoDB Documents by Using ```updateMany()```**

It accepts three arguments i.e. a filter document, an update document, and an options object. 

1. filter: It contains the selection criteria for the update. 

2. update: The update document, contains an update operator expression that will be used in the update. 

3. options: The third argument is an options object. Note that options is not a required argument. 


Syntax:

~~~js
db.<collection>.replaceOne(
    <filter>, 
    <update>, 
    {options}
);
~~~


~~~js
db.books.updateMany(
  { publishedDate: { $lt: new Date("2019-01-01") } },
  { $set: { status: "LEGACY" } }
)
~~~

