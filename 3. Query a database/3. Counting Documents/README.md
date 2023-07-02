# **Counting Documents in a MongoDB Collection**

~~~js
use sample_training;
~~~

Syntax : 

~~~js
db.<collection>.countDocuments(<query>, <options>);
~~~

Count number of documents in trip collection

~~~js
db.trips.countDocuments();
~~~
Output : 
~~~js
10000
~~~

Count number of trips over 120 minutes by subscribers
~~~js
db.trips.countDocuments({ tripduration: { $gt: 120 }, usertype: "Subscriber" })
~~~
Output : 
~~~js
7847
~~~