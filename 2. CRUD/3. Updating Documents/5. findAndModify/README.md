# **Updating MongoDB Documents by Using ```findAndModify()```**

It is used to return the document that has just been updated. 

For example, imagine we're creating an app that tracks the number of users who download a podcast. 

**```updateOne() + findOne()```**

One way to update and return the number of downloads is to use the updateOne and findOne methods. First, we would use updateOne to increment the downloads field, then we would use findOne to return the document by using the underscore ID. 

The problem with this approach is that it makes two round trips to the server where findAndModify is only one. Additionally, if we make our update via updateOne, another user could modify the document before our findOne, and we will get a different version of the document. 

To prevent this, we can use findAndModify. This is a powerful method that guarantees the correct version of the document will be returned without another thread modifying the document before we're able to view it. 

~~~js
db.podcasts.findAndModify({
  query: { _id: ObjectId("6261a92dfee1ff300dc80bf1") },
  update: { $inc: { subscribers: 1 } },
  new: true,
})
~~~

