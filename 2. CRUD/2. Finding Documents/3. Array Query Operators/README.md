# **Querying on Array Elements in MongoDB**

~~~js
use sample_analytics;
~~~

## **Find Documents with an Array That Contains a Specified Value**

~~~js
db.accounts.find({ products: "InvestmentFund"});
~~~

Output:

~~~js
[
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162391"),
    account_id: 383777,
    limit: 10000,
    products: [
      'CurrencyService',
      'Derivatives',
      'InvestmentFund',
      'Commodity',
      'InvestmentStock'
    ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162392"),
    account_id: 794875,
    limit: 9000,
    products: [ 'InvestmentFund', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162396"),
    account_id: 260499,
    limit: 10000,
    products: [ 'InvestmentFund', 'Derivatives', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816239e"),
    account_id: 299072,
    limit: 10000,
    products: [ 'InvestmentFund', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623a1"),
    account_id: 977982,
    limit: 10000,
    products: [
      'InvestmentFund',
      'Derivatives',
      'InvestmentStock',
      'CurrencyService'
    ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623a4"),
    account_id: 212024,
    limit: 10000,
    products: [ 'InvestmentFund', 'Brokerage', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623a5"),
    account_id: 433811,
    limit: 10000,
    products: [
      'CurrencyService',
      'InvestmentFund',
      'Brokerage',
      'InvestmentStock'
    ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623aa"),
    account_id: 403363,
    limit: 10000,
    products: [
      'CurrencyService',
      'InvestmentFund',
      'InvestmentStock',
      'Derivatives'
    ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623ac"),
    account_id: 276528,
    limit: 10000,
    products: [ 'InvestmentFund', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623ad"),
    account_id: 383701,
    limit: 10000,
    products: [ 'InvestmentFund', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623b0"),
    account_id: 463155,
    limit: 10000,
    products: [ 'Brokerage', 'InvestmentFund', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623b3"),
    account_id: 895735,
    limit: 10000,
    products: [
      'InvestmentFund',
      'CurrencyService',
      'Derivatives',
      'InvestmentStock'
    ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623b5"),
    account_id: 984021,
    limit: 10000,
    products: [ 'InvestmentFund', 'Derivatives', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623b6"),
    account_id: 503933,
    limit: 10000,
    products: [ 'InvestmentFund', 'InvestmentStock', 'Derivatives', 'Commodity' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623b8"),
    account_id: 475387,
    limit: 10000,
    products: [ 'InvestmentFund', 'Derivatives', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623b9"),
    account_id: 775690,
    limit: 10000,
    products: [ 'InvestmentFund', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623bb"),
    account_id: 136137,
    limit: 10000,
    products: [ 'Commodity', 'InvestmentStock', 'InvestmentFund', 'Derivatives' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623c0"),
    account_id: 522933,
    limit: 10000,
    products: [ 'InvestmentFund', 'Brokerage', 'Derivatives', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623c7"),
    account_id: 785786,
    limit: 10000,
    products: [
      'Derivatives',
      'InvestmentStock',
      'InvestmentFund',
      'CurrencyService'
    ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee581623c8"),
    account_id: 462501,
    limit: 10000,
    products: [ 'InvestmentFund', 'Commodity', 'InvestmentStock' ]
  }
]
Type "it" for more
~~~

## **Find a Document by Using the $elemMatch Operator**

The ```$elemMatch``` operator matches documents that contain an array field with at least one element that matches all the specified query criteria.

~~~js
{ <field>: { $elemMatch: { <query1>, <query2>, ... } } }
~~~


~~~js
db.accounts.find({ products: { $elemMatch: { $eq: "InvestmentStock" } } });
~~~

Output:

~~~js
[
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816238c"),
    account_id: 371138,
    limit: 9000,
    products: [ 'Derivatives', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816238d"),
    account_id: 557378,
    limit: 10000,
    products: [ 'InvestmentStock', 'Commodity', 'Brokerage', 'CurrencyService' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816238e"),
    account_id: 198100,
    limit: 10000,
    products: [ 'Derivatives', 'CurrencyService', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816238f"),
    account_id: 674364,
    limit: 10000,
    products: [ 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162390"),
    account_id: 278603,
    limit: 10000,
    products: [ 'Commodity', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162391"),
    account_id: 383777,
    limit: 10000,
    products: [
      'CurrencyService',
      'Derivatives',
      'InvestmentFund',
      'Commodity',
      'InvestmentStock'
    ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162392"),
    account_id: 794875,
    limit: 9000,
    products: [ 'InvestmentFund', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162393"),
    account_id: 328304,
    limit: 10000,
    products: [ 'Derivatives', 'InvestmentStock', 'CurrencyService' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162394"),
    account_id: 487188,
    limit: 10000,
    products: [ 'Brokerage', 'CurrencyService', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162395"),
    account_id: 910579,
    limit: 10000,
    products: [ 'Brokerage', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162396"),
    account_id: 260499,
    limit: 10000,
    products: [ 'InvestmentFund', 'Derivatives', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162397"),
    account_id: 668949,
    limit: 10000,
    products: [
      'Brokerage',
      'CurrencyService',
      'InvestmentStock',
      'Derivatives'
    ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162398"),
    account_id: 976027,
    limit: 10000,
    products: [ 'Brokerage', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee58162399"),
    account_id: 135185,
    limit: 10000,
    products: [ 'CurrencyService', 'Brokerage', 'InvestmentStock', 'Commodity' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816239a"),
    account_id: 370583,
    limit: 10000,
    products: [ 'Brokerage', 'Commodity', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816239b"),
    account_id: 870466,
    limit: 10000,
    products: [ 'Derivatives', 'Brokerage', 'Commodity', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816239c"),
    account_id: 692278,
    limit: 10000,
    products: [ 'Commodity', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816239d"),
    account_id: 864905,
    limit: 10000,
    products: [ 'Commodity', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816239e"),
    account_id: 299072,
    limit: 10000,
    products: [ 'InvestmentFund', 'InvestmentStock' ]
  },
  {
    _id: ObjectId("5ca4bbc7a2dd94ee5816239f"),
    account_id: 137994,
    limit: 10000,
    products: [ 'CurrencyService', 'InvestmentStock' ]
  }
]
Type "it" for more
~~~

## **```$all```**

The ```$all``` operator selects the documents where the value of a field is an array that contains all the specified elements. To specify an ```$all``` expression, use the following prototype:

~~~js
{ <field>: { $all: [ <value1> , <value2> ... ] } }
~~~

## **```$size```**

The ```$size``` operator matches any array with the number of elements specified by the argument.

Syntax:

~~~js
db.<collection>.find( { field: { $size: <number> } } );
~~~

```$size``` does not accept ranges of values.

