# **Finding Documents by Using Comparison Operators**

In MongoDB, we work with the following operators: 

1. $gt (greater than)
2. $lt (less than)
3. $lte (less than or equal to)
4. $gte (greater than or equal to). 

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
