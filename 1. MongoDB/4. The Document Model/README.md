# **The MongoDB Document Model**

MongoDB stores data in structures known as documents, that's why it's classified as a document database. 

The MongoDB database structures data in documents which are similar to JSON objects. 

## **BSON**

Documents are displayed in a JSON format, they're stored in the database in a format called BSON. 

BSON, short for binary JSON, is an extension of JSON providing additional features that MongoDB can leverage. 

BSON also adds support for additional data types unavailable in standard JSON. 

Because MongoDB stores data in BSON, the database can support a huge range of data types, including all the JSON data types such as string, object, array, Boolean, and null, as well as dates, different types of numbers, object IDs, and more. 

ObjectID is a special data type used in MongoDB to create unique identifiers. In the database, every document requires an ID field that acts as a primary key. If an inserted document doesn't include the ID field, MongoDB will automatically add it and generate an object ID value for it. 


## **Polymorphic Pattern**

By default, MongoDB supports a flexible schema model and polymorphic data. This allows us to store documents with different structures in the same collection together. 

Documents can contain different fields, and fields may contain different data types from one document to the next. 

This is unlike relational databases in which it's necessary to declare a table schema before you begin inserting data. 

MongoDB's flexible schema enables us to iterate quickly and evolve as our requirements change. 

With a relational database, we'd run into a complex chain of dependencies for even a trivial change like this one. Writing schema change scripts, coordinating across engineering teams, and downtime when the script executes. All of this would slow us down. 

To make schema changes with MongoDB, we simply update our classes to include new fields and start inserting documents with the new schema. 

If we want to have more control over the structure and content of our database, we can add optional schema validation rules to set constraints on the structure of documents in the collection. 