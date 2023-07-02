# **Introduction to MongoDB Aggregation**

~~~js
use sample_training;
~~~

## **Aggregation :**
An analysis and summary of data. 

## **Aggregation Stage :**
An aggregation stage is an aggregation operation that is performed on the data and does not permanently alter the source data.

## **Aggregation Pipeline :**
A series of aggregation stages completed one at a time in order. We can string together aggregation stages to create a pipeline. A pipeline consists of multiple stages where data can be 
1. Filtered 
2. Sorted
3. Grouped 
4. Transformed

Documents that are output from one stage become input into the next stage.

Syntax:
~~~js
db.<collection>.aggregate([
    { $stage_name: { <expression> } },
    { $stage_name: { <expression> } }
])
~~~

## **Some of the commonly used stages are** 

### **$match**

1. It filters for data that matches certain criteria.
2. Place as early as possible in the pipeline so it can use indexes.
3. It reduces the number of documents.
4. It lessens the processing required. 

**examples**

~~~js
$match : { student_id : 1234}
~~~

~~~js
$match : { grades : { $gte : 85 } }
~~~

~~~js
db.zips.aggregate([ { $match: {state: "CA" } } ]);
~~~
Output :
~~~js
[
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f35d"),
    city: 'LOS ANGELES',
    zip: '90002',
    loc: { y: 33.94969, x: 118.246213 },
    pop: 40629,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f35e"),
    city: 'LOS ANGELES',
    zip: '90003',
    loc: { y: 33.965335, x: 118.272739 },
    pop: 53938,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f360"),
    city: 'LOS ANGELES',
    zip: '90004',
    loc: { y: 34.076163, x: 118.302863 },
    pop: 64062,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f361"),
    city: 'LOS ANGELES',
    zip: '90001',
    loc: { y: 33.973093, x: 118.247896 },
    pop: 51841,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f362"),
    city: 'LOS ANGELES',
    zip: '90005',
    loc: { y: 34.058508, x: 118.301197 },
    pop: 35864,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f363"),
    city: 'LOS ANGELES',
    zip: '90007',
    loc: { y: 34.029442, x: 118.287095 },
    pop: 46985,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f364"),
    city: 'LOS ANGELES',
    zip: '90010',
    loc: { y: 34.060633, x: 118.302664 },
    pop: 5335,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f365"),
    city: 'LOS ANGELES',
    zip: '90008',
    loc: { y: 34.011643, x: 118.341123 },
    pop: 33073,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f366"),
    city: 'LOS ANGELES',
    zip: '90011',
    loc: { y: 34.007856, x: 118.258189 },
    pop: 96074,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f367"),
    city: 'LOS ANGELES',
    zip: '90012',
    loc: { y: 34.061396, x: 118.238479 },
    pop: 28518,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f368"),
    city: 'LOS ANGELES',
    zip: '90013',
    loc: { y: 34.044841, x: 118.243366 },
    pop: 5653,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f369"),
    city: 'LOS ANGELES',
    zip: '90015',
    loc: { y: 34.043439, x: 118.271613 },
    pop: 18880,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f36a"),
    city: 'LOS ANGELES',
    zip: '90016',
    loc: { y: 34.029826, x: 118.352787 },
    pop: 43669,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f36b"),
    city: 'LOS ANGELES',
    zip: '90006',
    loc: { y: 34.049323, x: 118.291687 },
    pop: 63389,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f36c"),
    city: 'LOS ANGELES',
    zip: '90017',
    loc: { y: 34.055864, x: 118.266582 },
    pop: 21790,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f36d"),
    city: 'LOS ANGELES',
    zip: '90018',
    loc: { y: 34.028972, x: 118.315173 },
    pop: 48267,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f36e"),
    city: 'LOS ANGELES',
    zip: '90021',
    loc: { y: 34.033303, x: 118.244698 },
    pop: 2869,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f36f"),
    city: 'LOS ANGELES',
    zip: '90020',
    loc: { y: 34.066535, x: 118.302211 },
    pop: 34926,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f370"),
    city: 'LOS ANGELES',
    zip: '90014',
    loc: { y: 34.044272, x: 118.250937 },
    pop: 2715,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f371"),
    city: 'LOS ANGELES',
    zip: '90023',
    loc: { y: 34.024478, x: 118.197498 },
    pop: 47136,
    state: 'CA'
  }
]
Type "it" for more
~~~

### **$group**

1. It groups documents based on criteria. It groups documents by a group key. 
2. Output is one document for each unique value of the group key. 

Syntax:

~~~js
db.<collection>.aggregate([
    { 
        $group: 
        {
            _id : <expression>, //Group key
            <field>: { accumulator: <expression> }
        }
    }
])
~~~

~~~js
db.zips.aggregate([ { $group: { _id: "$city", totalZips: { $count: {} } } } ]);
~~~
Output :
~~~js
[
  { _id: 'SLATERSVILLE', totalZips: 1 },
  { _id: 'BOTKINS', totalZips: 1 },
  { _id: 'BRUCETON', totalZips: 1 },
  { _id: 'NEW MEADOWS', totalZips: 1 },
  { _id: 'HARWOOD', totalZips: 3 },
  { _id: 'BREESPORT', totalZips: 1 },
  { _id: 'WEST PARIS', totalZips: 1 },
  { _id: 'HOLDREGE', totalZips: 1 },
  { _id: 'HANSKA', totalZips: 1 },
  { _id: 'SEDALIA', totalZips: 2 },
  { _id: 'SUMERCO', totalZips: 1 },
  { _id: 'SURREY', totalZips: 1 },
  { _id: 'RYAN', totalZips: 2 },
  { _id: 'PUYALLUP', totalZips: 4 },
  { _id: 'LORMAN', totalZips: 1 },
  { _id: 'APALACHIN', totalZips: 1 },
  { _id: 'FLORISSANT', totalZips: 4 },
  { _id: 'DUDLEY', totalZips: 5 },
  { _id: 'MOORESTOWN', totalZips: 2 },
  { _id: 'INTERLAKEN', totalZips: 1 }
]
Type "it" for more
~~~

**$match and $group**

~~~js
db.zips.aggregate([ { $match: {state: "CA" } },  { $group: { _id: "$city", totalZips: { $count: {} } } } ]);
~~~
Output :
~~~js
[
  { _id: 'HURON', totalZips: 1 },
  { _id: 'GILROY', totalZips: 1 },
  { _id: 'TWENTYNINE PALMS', totalZips: 2 },
  { _id: 'BASSETT', totalZips: 1 },
  { _id: 'OAKHURST', totalZips: 1 },
  { _id: 'CALABASAS', totalZips: 1 },
  { _id: 'RESEDA', totalZips: 1 },
  { _id: 'DAGGETT', totalZips: 1 },
  { _id: 'DENAIR', totalZips: 1 },
  { _id: 'CITRUS HEIGHTS', totalZips: 2 },
  { _id: 'SAMOA', totalZips: 1 },
  { _id: 'CLIO', totalZips: 1 },
  { _id: 'SIERRA MADRE', totalZips: 1 },
  { _id: 'PRINCETON', totalZips: 1 },
  { _id: 'ROSSMOOR', totalZips: 1 },
  { _id: 'OJAI', totalZips: 1 },
  { _id: 'TOLLHOUSE', totalZips: 1 },
  { _id: 'CRYSTALAIRE', totalZips: 1 },
  { _id: 'HARBOR CITY', totalZips: 1 },
  { _id: 'PLEASANTON', totalZips: 2 }
]
Type "it" for more
~~~

### **$sort**

1. It puts the documents in a specified order. It sorts all input documents and passes them through the pipeline in sorted order. 

2. We specify 1 for ascending order and -1 for descending order. 

~~~js
db.zips.findOne();
~~~
Output :
~~~js
{
  _id: ObjectId("5c8eccc1caa187d17ca6ed16"),
  city: 'ALPINE',
  zip: '35014',
  loc: { y: 33.331165, x: 86.208934 },
  pop: 3062,
  state: 'AL'
}
~~~

~~~js
db.zips.aggregate([ { $sort: { pop: -1 } } ]);
~~~
Output :
~~~js
[
  {
    _id: ObjectId("5c8eccc1caa187d17ca7044d"),
    city: 'CHICAGO',
    zip: '60623',
    loc: { y: 41.849015, x: 87.7157 },
    pop: 112047,
    state: 'IL'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca7307f"),
    city: 'BROOKLYN',
    zip: '11226',
    loc: { y: 40.646694, x: 73.956985 },
    pop: 111396,
    state: 'NY'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca72fa0"),
    city: 'NEW YORK',
    zip: '10021',
    loc: { y: 40.768476, x: 73.958805 },
    pop: 106564,
    state: 'NY'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca72fa5"),
    city: 'NEW YORK',
    zip: '10025',
    loc: { y: 40.797466, x: 73.968312 },
    pop: 100027,
    state: 'NY'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f39d"),
    city: 'BELL GARDENS',
    zip: '90201',
    loc: { y: 33.969177, x: 118.17205 },
    pop: 99568,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca70447"),
    city: 'CHICAGO',
    zip: '60617',
    loc: { y: 41.725743, x: 87.556012 },
    pop: 98612,
    state: 'IL'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f366"),
    city: 'LOS ANGELES',
    zip: '90011',
    loc: { y: 34.007856, x: 118.258189 },
    pop: 96074,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca70466"),
    city: 'CHICAGO',
    zip: '60647',
    loc: { y: 41.920903, x: 87.704322 },
    pop: 95971,
    state: 'IL'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca70455"),
    city: 'CHICAGO',
    zip: '60628',
    loc: { y: 41.693443, x: 87.624277 },
    pop: 94317,
    state: 'IL'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f3db"),
    city: 'NORWALK',
    zip: '90650',
    loc: { y: 33.90564, x: 118.081767 },
    pop: 94188,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca7044a"),
    city: 'CHICAGO',
    zip: '60620',
    loc: { y: 41.741119, x: 87.654251 },
    pop: 92005,
    state: 'IL'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca70454"),
    city: 'CHICAGO',
    zip: '60629',
    loc: { y: 41.778149, x: 87.706936 },
    pop: 91814,
    state: 'IL'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca7043e"),
    city: 'CHICAGO',
    zip: '60609',
    loc: { y: 41.809721, x: 87.653279 },
    pop: 89762,
    state: 'IL'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca70448"),
    city: 'CHICAGO',
    zip: '60618',
    loc: { y: 41.946401, x: 87.704214 },
    pop: 88377,
    state: 'IL'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca730a1"),
    city: 'JACKSON HEIGHTS',
    zip: '11373',
    loc: { y: 40.740388, x: 73.878551 },
    pop: 88241,
    state: 'NY'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f423"),
    city: 'ARLETA',
    zip: '91331',
    loc: { y: 34.258081, x: 118.420692 },
    pop: 88114,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca73072"),
    city: 'BROOKLYN',
    zip: '11212',
    loc: { y: 40.662474, x: 73.914483 },
    pop: 87079,
    state: 'NY'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f3b7"),
    city: 'SOUTH GATE',
    zip: '90280',
    loc: { y: 33.94617, x: 118.201349 },
    pop: 87026,
    state: 'CA'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca730a4"),
    city: 'RIDGEWOOD',
    zip: '11385',
    loc: { y: 40.703613, x: 73.896122 },
    pop: 85732,
    state: 'NY'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca72fd3"),
    city: 'BRONX',
    zip: '10467',
    loc: { y: 40.873671, x: 73.871242 },
    pop: 85710,
    state: 'NY'
  }
]
Type "it" for more
~~~

### **$limit**
It limits the number of documents that are passed on to the next aggregation stage. 

~~~js
db.zips.aggregate([ { $sort: { pop: -1 } }, { $limit: 3 } ]);
~~~
Output
~~~js
[
  {
    _id: ObjectId("5c8eccc1caa187d17ca7044d"),
    city: 'CHICAGO',
    zip: '60623',
    loc: { y: 41.849015, x: 87.7157 },
    pop: 112047,
    state: 'IL'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca7307f"),
    city: 'BROOKLYN',
    zip: '11226',
    loc: { y: 40.646694, x: 73.956985 },
    pop: 111396,
    state: 'NY'
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca72fa0"),
    city: 'NEW YORK',
    zip: '10021',
    loc: { y: 40.768476, x: 73.958805 },
    pop: 106564,
    state: 'NY'
  }
]
~~~

The order of stages matters. If we do first limit then sort, it would have sorted first three documents. 

### **$project**

It determines the output shape. It allows us to specify the existing or new fields that will be returned by the aggregation. 

This stage performs a projection similar to the one we apply in ```find()``` operations. 

It should usually be the last stage, because it specifies the exact fields in the output. MongoDB already works out which fields are needed and reads only the fields that are required in the pipeline, so there's usually no reason to use project earlier in the pipeline. 

Projection can be specified as either inclusion or exclusion. 

~~~js
db.<collection>.aggregate([
    { $project : {
        <field>: <value>,
        <field>: <value>,
        ....
        <field>: <value>
    }}
])
~~~

~~~js
$project : { <field>: 1 } 
~~~

~~~js
$project : { <field>: 0 } 
~~~

In the project stage, either include the fields you would like to keep by setting the value to 1, or set the value to 0 if you are specifying the fields you want to exclude. 

~~~js
$project : { <field>: <new value> } 
~~~

If the projected fields are new fields, we can specify the value that we want to assign to them. You can also specify a new value to existing fields in project.

~~~js
$project : { total: { $sum : [ "$quiz", "$homework" ] } }
~~~

~~~js
db.zips.aggregate([ { $project: { state: 1, zipcode: "$zip", population: "$pop", _id: 0 } }, { $limit: 3 } ]);
~~~
Output :
~~~
[
  { state: 'AL', zipcode: '35014', population: 3062 },
  { state: 'AL', zipcode: '35020', population: 40549 },
  { state: 'AL', zipcode: '35004', population: 6055 }
]
~~~


### **$set**

1. Rather than specifying output like project, the set stage adds or modifies fields in the pipeline. 

2. This is useful when we want to change existing fields in the pipeline or add new ones to be used in upcoming pipeline stages without having to specify all the existing fields. 

~~~js
db.<collection>.aggregate([
    { $set : {
        <field>: <value>,
        <field>: <value>,
        ....
        <field>: <value>
    }}
])
~~~

The set stage takes the field names and values that we want to add or change. 

~~~js
$set : { defaultUsername : { $concat: [ "$first_name", "$last_name" ] } }
~~~

~~~js
db.zips.aggregate([ { $set: { pop_2022: { $round: { $multiply: [1.0031, "$pop"] } }}}, {$limit: 3} ]);
~~~
Output :
~~~js
[
  {
    _id: ObjectId("5c8eccc1caa187d17ca6ed16"),
    city: 'ALPINE',
    zip: '35014',
    loc: { y: 33.331165, x: 86.208934 },
    pop: 3062,
    state: 'AL',
    pop_2022: 3071
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6ed17"),
    city: 'BESSEMER',
    zip: '35020',
    loc: { y: 33.409002, x: 86.947547 },
    pop: 40549,
    state: 'AL',
    pop_2022: 40675
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6ed18"),
    city: 'ACMAR',
    zip: '35004',
    loc: { y: 33.584132, x: 86.51557 },
    pop: 6055,
    state: 'AL',
    pop_2022: 6074
  }
]
~~~

### **$count**

It counts the number of documents in the pipeline and returns the total count. 

~~~js
{ $count: <field name> }
~~~

The count stage receives a string that represents the new fields that's returned with the total document count. 


~~~js
db.zips.aggregate([ { $count: "num_of_documents" } ]);
~~~
Output :
~~~
[ { num_of_documents: 29470 } ]
~~~

Note that the output of this aggregation pipeline is a single document with only one field, which is num_of_documents. 

### **$out**

1. It writes documents that are returned by an aggregation pipleline into a collection. 
2. So, It must be the last stage of the pipeline.
3. It creates a new collection if it does not already exist.
4. If the collection exists, ```$out``` replaces the existing collection with new data. 

~~~js
{ $out : { db: "<db>", coll: "<new collection>" } }
~~~

~~~js
{ $out : "<new collection>"  }
~~~

Here, ```$out``` uses the same database. 

~~~js
db.zips.aggregate([ 
    { $group: {_id: "$state", total_pop: { $sum: "$pop" }}},
    { $match: { total_pop: { $lt: 1000000 } } },
    { $out: "small_states" } 
])
~~~

We can confirm using 

~~~js
show collections;
~~~
or
~~~js
db.small_states.find();
~~~




