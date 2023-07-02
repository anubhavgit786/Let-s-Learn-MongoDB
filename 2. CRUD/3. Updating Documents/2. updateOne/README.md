# **Updating MongoDB Documents by Using ```updateOne()```**

This method updates a single document. It accepts three arguments i.e. a filter document, an update document, and an options object. 

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

## **```$set``` Operator**

The $set operator does one of two things, it adds new fields and values to a document, or it replaces the value of a field with a specified value. 

Imagine that you manage a database called audio, that contains a collection called podcasts. You need to update a podcast document with a new subscriber count and host. You can use the updateOne method and update operators to make these changes. 

~~~js
db.podcasts.updateOne(
    { _id: ObjectId("5e8f8f8f8f8f8f8f8f8f8f8") },
    { $set: { subscribers: 98562, }}
)
~~~

## **```$push``` Operator**

The $push operator does one of two things, it appends a value to an array or if the field is absent, $push adds the array field with the value as its element. 

~~~js
db.podcasts.updateOne(
  { _id: ObjectId("5e8f8f8f8f8f8f8f8f8f8f8") },
  { $push: { hosts: "Nic Raboy" } }
)
~~~

## **```upsert```**

If the update filter doesn't match any documents, then no update occurs. In this case, we might want to create a document. This is what the $upsert option allows us to do.

Insert a document with the provided information if matching documents don't exist. The $upsert option is short for update or insert. 


When the filter that gets passed to the updateOne method yields no matching documents, we can use $upsert to insert a document with the provided information into the collection. 

In either case, the update operations provided in the update document will be carried out, either on the match document or on the document that was just inserted. 

~~~js
db.podcasts.updateOne(
  { title: "The Developer Hub" },
  { $set: { topics: ["databases", "MongoDB"] } },
  { upsert: true }
)
~~~

