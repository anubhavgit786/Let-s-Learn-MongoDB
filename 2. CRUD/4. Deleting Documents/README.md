# Deleting Documents in MongoDB

To delete documents, use the ```deleteOne()``` or ```deleteMany()``` methods. Both methods accept a filter document and an options object.

## Delete One Document

~~~js
db.podcasts.deleteOne({ _id: Objectid("6282c9862acb966e76bbf20a") })
~~~

## Delete Many Documents

~~~js
db.podcasts.deleteMany({category: “crime”})
~~~

