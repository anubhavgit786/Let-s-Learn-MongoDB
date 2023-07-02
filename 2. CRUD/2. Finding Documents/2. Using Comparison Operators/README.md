# **Finding Documents by Using Comparison Operators**

In MongoDB, we work with the following operators: 

1. $gt (greater than)
2. $lt (less than)
3. $lte (less than or equal to)
4. $gte (greater than or equal to). 
5. $in
6. $nin
7. $eq
8. $ne

Syntax:

~~~js

db.<collection>.find({ 
    <field>: { <operator>: <value> } 
});

~~~

e.g.

~~~js

use sample_supplies;

~~~

~~~js

db.sales.findOne();

~~~

Ouptput:

~~~js
{
  _id: ObjectId("5bd761dcae323e45a93ccfe8"),
  saleDate: ISODate("2015-03-23T21:06:49.506Z"),
  items: [
    {
      name: 'printer paper',
      tags: [ 'office', 'stationary' ],
      price: Decimal128("40.01"),
      quantity: 2
    },
    {
      name: 'notepad',
      tags: [ 'office', 'writing', 'school' ],
      price: Decimal128("35.29"),
      quantity: 2
    },
    {
      name: 'pens',
      tags: [ 'writing', 'office', 'school', 'stationary' ],
      price: Decimal128("56.12"),
      quantity: 5
    },
    {
      name: 'backpack',
      tags: [ 'school', 'travel', 'kids' ],
      price: Decimal128("77.71"),
      quantity: 2
    },
    {
      name: 'notepad',
      tags: [ 'office', 'writing', 'school' ],
      price: Decimal128("18.47"),
      quantity: 2
    },
    {
      name: 'envelopes',
      tags: [ 'stationary', 'office', 'general' ],
      price: Decimal128("19.95"),
      quantity: 8
    },
    {
      name: 'envelopes',
      tags: [ 'stationary', 'office', 'general' ],
      price: Decimal128("8.08"),
      quantity: 3
    },
    {
      name: 'binder',
      tags: [ 'school', 'general', 'organization' ],
      price: Decimal128("14.16"),
      quantity: 3
    }
  ],
  storeLocation: 'Denver',
  customer: { gender: 'M', age: 42, email: 'cauho@witwuta.sv', satisfaction: 4 },
  couponUsed: true,
  purchaseMethod: 'Online'
}
~~~

~~~js
db.sales.find({ "items.price": { $gt: 50}});
db.sales.find({ "items.price": { $lt: 50}});
~~~

~~~js
db.sales.find({ "customer.age": { $lte: 65}});
db.sales.find({ "customer.age": { $gte: 65}});
~~~

## **```$in``` Operator**

The in operator allows us to select all documents that have a field value equal to any of the values specified in the array. 

Syntax: 

~~~js

db.<collection>.find({ 
    <field>: { $in: 
        [ <value 1>, <value 2>, <value 3>, ..... <value N> ] 
    } 
});

~~~

e.g.

~~~js

db.zips.find({ city: { $in: [ "PHOENIX", "CHICAGO" ]} }).pretty();

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
  },
  {
    _id: ObjectId("5c8eccc1caa187d17ca6f025"),
    city: 'PHOENIX',
    zip: '85028',
    loc: { y: 33.585115, x: 112.008724 },
    pop: 22662,
    state: 'AZ'
  }
]
Type "it" for more
~~~

## **```$nin``` Operator**

Syntax: 
~~~js
{ field: { $nin: [ <value1>, <value2> ... <valueN> ] } }
~~~
```$nin``` selects the documents where:

1. the field value is not in the specified array or

2. the field does not exist.

## **```$eq``` Operator**

~~~js
{ <field>: { $eq: <value> } }
~~~

The ``$eq`` operator matches documents where the value of a field equals the specified value.

## **```$ne``` Operator**

~~~js
{ <field>: { $ne: <value> } }
~~~

The ``$ne`` selects the documents where the value of the field is not equal to the specified value. This includes documents that do not contain the field.

