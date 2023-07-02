# ```replaceOne()```

To replace documents in MongoDB, we use the replaceOne() method. The replaceOne() method takes the following parameters:

1. filter: A query that matches the document to replace.

2. replacement: The new document to replace the old one with.

3. options: An object that specifies options for the update.

Syntax:

~~~js
db.<collection>.replaceOne(filter, replacement, options);
~~~