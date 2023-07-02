# **Finding Documents in a MongoDB Collection**

~~~js

use sample_training;

~~~

Syntax:

~~~js

db.<collection>.find()

~~~

~~~js

db.zips.find().pretty();

~~~

This returns a cursor with the results. The shell will automatically iterate through our cursor once the results are returned. 

To see more results, we can use the ```it``` shell directive, which will iterate through the long list of results.


Now, let's say we want to retrieve a specific document from our collection. We can do this in two ways. 

Syntax:

~~~js

db.<collection>.find({ field: { $eq: <value> }});

~~~

or 

~~~js

db.<collection>.find({ field: <value> });

~~~

e.g.

~~~js

db.zips.find({ state: "AZ" }).pretty();

~~~

Output:

~~~js

[
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f010"),
    city: 'PHOENIX',
    zip: '85012',
    loc: { y: 33.509744, x: 112.067816 },
    pop: 6141,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f011"),
    city: 'PHOENIX',
    zip: '85004',
    loc: { y: 33.455708, x: 112.068584 },
    pop: 4491,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f012"),
    city: 'PHOENIX',
    zip: '85009',
    loc: { y: 33.456373, x: 112.128368 },
    pop: 41512,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f013"),
    city: 'PHOENIX',
    zip: '85006',
    loc: { y: 33.465016, x: 112.047357 },
    pop: 26747,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f014"),
    city: 'PHOENIX',
    zip: '85014',
    loc: { y: 33.510263, x: 112.05557 },
    pop: 22646,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f015"),
    city: 'PHOENIX',
    zip: '85015',
    loc: { y: 33.508164, x: 112.101064 },
    pop: 32497,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f016"),
    city: 'PHOENIX',
    zip: '85013',
    loc: { y: 33.508493, x: 112.082657 },
    pop: 18467,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f017"),
    city: 'PHOENIX',
    zip: '85008',
    loc: { y: 33.466457, x: 111.998381 },
    pop: 41733,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f018"),
    city: 'PHOENIX',
    zip: '85019',
    loc: { y: 33.512284, x: 112.141681 },
    pop: 21879,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f019"),
    city: 'PHOENIX',
    zip: '85017',
    loc: { y: 33.515263, x: 112.121232 },
    pop: 27741,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f01b"),
    city: 'PHOENIX',
    zip: '85023',
    loc: { y: 33.632383, x: 112.111838 },
    pop: 54668,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f01c"),
    city: 'PHOENIX',
    zip: '85007',
    loc: { y: 33.452298, x: 112.089326 },
    pop: 13650,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f01d"),
    city: 'PHOENIX',
    zip: '85020',
    loc: { y: 33.562281, x: 112.055888 },
    pop: 29043,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f01e"),
    city: 'PHOENIX',
    zip: '85024',
    loc: { y: 33.661664, x: 112.036956 },
    pop: 14090,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f01f"),
    city: 'PHOENIX',
    zip: '85018',
    loc: { y: 33.495796, x: 111.988259 },
    pop: 32926,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f020"),
    city: 'NEW RIVER STAGE',
    zip: '85027',
    loc: { y: 33.667157, x: 112.102723 },
    pop: 24843,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f021"),
    city: 'PHOENIX',
    zip: '85022',
    loc: { y: 33.631513, x: 112.052008 },
    pop: 33573,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f022"),
    city: 'PHOENIX',
    zip: '85021',
    loc: { y: 33.559965, x: 112.092686 },
    pop: 31201,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f023"),
    city: 'PHOENIX',
    zip: '85003',
    loc: { y: 33.451095, x: 112.077428 },
    pop: 10633,
    state: 'AZ'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f024"),
    city: 'PHOENIX',
    zip: '85016',
    loc: { y: 33.502117, x: 112.030496 },
    pop: 29527,
    state: 'AZ'
  }
]
Type "it" for more
~~~