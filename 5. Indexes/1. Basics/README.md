# Using MongoDB Indexes in Collections

1. Indexes are special data structures that store a small portion of the collections data in an ordered form that is easy to traverse and search efficiently. 

2. Indexes point to the document identity and allow you to look up access and update data faster. 

3. Indexes are used in MongoDB to improve query performance. They can speed up queries, reduce disk IO, and reduce the resources required for them. 

4. Indexes also support queries such as equality matches and range based operations and return sorted results. 

5. Indexes store data in an ordered form based on the index fields and values so ordered that are provided when the index is created. 

## Without Indexes

MongoDB has to read every document in a collection by performing a collection scan to check if it matches the query being run. 

Also needs to sort the results in memory if the query requires a sorted output. 

## With Indexes

MongoDB only fetches the documents identified by the index based on the query and returns the results faster. 

If the index includes all the information the query wants to retrieve, MongoDB does not need to read the document. 

By default, there is only one index created per collection. This default index only includes the _id field. 

Every query should use an index. This way, you can create additional indexes in your collections to cover your data queries. 

## Note

Be aware that indexes come with a right performance cost. 

When we insert new documents in the collection or update the index fields in them, we also need to update the data in the index structure. Also, right performance can degrade if we have too many indexes in a collection. 

We need to make sure that all the indexes we have are being used. Otherwise, we should delete the unnecessary or redundant indexes. 

## Most Common Index Types :

1. Single field indexes are indexes on one field only. 

2. Compound indexes include more than one field in the index. 

3. In both these indexes, the starting fields or index prefix can be used to support queries. 

4. Both index types can also be multikey indexes if they operate on an array field. Each array entry has a corresponding index entry. 

