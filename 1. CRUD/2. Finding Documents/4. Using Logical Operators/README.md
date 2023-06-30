# Logical Operators

~~~js
use sample_training;
~~~

## Logical AND

Syntax:

~~~js
db.<collection>.find({
    $and: [
        < expression 1 >,
        < expression 2 >,
        < expression 3 >
    ]

});
~~~

Implicit Expression

~~~js
db.<collection>.find({
    < expression 1 >,
    < expression 2 >,
    < expression 3 >
})
~~~

~~~js
db.routes.findOne();
~~~

Output:

~~~js
{
  _id: ObjectId("56e9b39b732b6122f877fa31"),
  airline: { id: 410, name: 'Aerocondor', alias: '2B', iata: 'ARD' },
  src_airport: 'CEK',
  dst_airport: 'KZN',
  codeshare: '',
  stops: 0,
  airplane: 'CR2'
}
~~~

~~~js
db.routes.find({ "airline.name": "Southwest Airlines", stops: { $gte: 1 } });
~~~

Output:

~~~js
[
  {
    _id: ObjectId("56e9b39c732b6122f878f280"),
    airline: { id: 4547, name: 'Southwest Airlines', alias: 'WN', iata: 'SWA' },
    src_airport: 'BOS',
    dst_airport: 'MCO',
    codeshare: '',
    stops: 1,
    airplane: '73W'
  },
  {
    _id: ObjectId("56e9b39c732b6122f878f45b"),
    airline: { id: 4547, name: 'Southwest Airlines', alias: 'WN', iata: 'SWA' },
    src_airport: 'MCO',
    dst_airport: 'BOS',
    codeshare: '',
    stops: 1,
    airplane: '73W'
  },
  {
    _id: ObjectId("56e9b39c732b6122f878f45e"),
    airline: { id: 4547, name: 'Southwest Airlines', alias: 'WN', iata: 'SWA' },
    src_airport: 'MCO',
    dst_airport: 'CAK',
    codeshare: '',
    stops: 1,
    airplane: '73C 73W'
  }
]
~~~

## Logical OR

Syntax:

~~~js
db.<collection>.find({
    $or: [
        < expression 1 >,
        < expression 2 >,
        < expression 3 >
    ]

});
~~~

~~~js
db.routes.find({
    $or: [{ dst_airport: "SEA" }, { src_airport: "SEA" }],
});
~~~

Output:

~~~js
[
  {
    _id: ObjectId("56e9b39b732b6122f8780cfc"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'BOS',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780d0f"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'BUR',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780dbd"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'CLT',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: '320 321 319'
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780e58"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'DEN',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780eef"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'DFW',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: '738 757'
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780f50"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'EWR',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781038"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'JFK',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: 738
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781051"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'KTN',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 734
  },
  {
    _id: ObjectId("56e9b39b732b6122f87810a1"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'LAX',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f87810d5"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'LGB',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 'CR7'
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781128"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'LHR',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: 777
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781170"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'MCI',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f878117e"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'MCO',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781206"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'MIA',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: 757
  },
  {
    _id: ObjectId("56e9b39b732b6122f878126f"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'OAK',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781282"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'ONT',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f87812e7"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'ORD',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: 738
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781327"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'PEK',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 787
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781392"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'PHL',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: '320 321'
  },
  {
    _id: ObjectId("56e9b39b732b6122f87813e0"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'PHX',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: '320 321'
  }
]
Type "it" for more
~~~


## Combined

Syntax:

~~~js
db.<collection>.find({
    $and:[
        { $or: [
            < expression 1 >,
            < expression 2 >,
            < expression 3 >
        ]},
        { $or: [
            < expression 1 >,
            < expression 2 >,
            < expression 3 >
        ]}
    ]
});
~~~

Note: When including the same operator more than once in your query, you need to use the explicit $and operator.

~~~js
 db.routes.find({
    $and: [
        { $or: [{ dst_airport: "SEA" }, { src_airport: "SEA" }] },
        { $or: [{ "airline.name": "American Airlines" }, { airplane: 320 }] },
    ]
});
~~~

Output:

~~~js
[
  {
    _id: ObjectId("56e9b39b732b6122f8780cfc"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'BOS',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780d0f"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'BUR',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780dbd"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'CLT',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: '320 321 319'
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780e58"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'DEN',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780eef"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'DFW',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: '738 757'
  },
  {
    _id: ObjectId("56e9b39b732b6122f8780f50"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'EWR',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781038"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'JFK',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: 738
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781051"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'KTN',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 734
  },
  {
    _id: ObjectId("56e9b39b732b6122f87810a1"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'LAX',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f87810d5"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'LGB',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 'CR7'
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781128"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'LHR',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: 777
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781170"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'MCI',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f878117e"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'MCO',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781206"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'MIA',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: 757
  },
  {
    _id: ObjectId("56e9b39b732b6122f878126f"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'OAK',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781282"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'ONT',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 737
  },
  {
    _id: ObjectId("56e9b39b732b6122f87812e7"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'ORD',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: 738
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781327"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'PEK',
    dst_airport: 'SEA',
    codeshare: 'Y',
    stops: 0,
    airplane: 787
  },
  {
    _id: ObjectId("56e9b39b732b6122f8781392"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'PHL',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: '320 321'
  },
  {
    _id: ObjectId("56e9b39b732b6122f87813e0"),
    airline: { id: 24, name: 'American Airlines', alias: 'AA', iata: 'AAL' },
    src_airport: 'PHX',
    dst_airport: 'SEA',
    codeshare: '',
    stops: 0,
    airplane: '320 321'
  }
]
Type "it" for more
~~~
