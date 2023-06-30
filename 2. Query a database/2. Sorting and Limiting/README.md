# Sorting and Limiting Query Results in MongoDB

~~~js
use sample_training;
~~~

## Sorting

Syntax:

~~~js
db.<collection>.find(filter, projection).sort({ <field> : 1});
~~~

```{ <field> : 1}``` means sort by ascending order and ```{ <field> : -1}``` means sort by descending order. 

~~~js
db.companies.find({category_code: "music"}, {name: 1}).sort({name: 1});
~~~

Output: 

~~~js
[
  { _id: ObjectId("52cdef7e4bab8bd67529ba19"), name: 'Audocs' },
  { _id: ObjectId("52cdef7d4bab8bd675299bb3"), name: 'Band Metrics' },
  { _id: ObjectId("52cdef7d4bab8bd675298de2"), name: 'Bandsintown' },
  { _id: ObjectId("52cdef7e4bab8bd67529a67f"), name: 'Club Cooee' },
  { _id: ObjectId("52cdef7d4bab8bd675298d51"), name: 'MIKESTAR' },
  { _id: ObjectId("52cdef7c4bab8bd675297fed"), name: 'Myxer' },
  { _id: ObjectId("52cdef7d4bab8bd675298d6e"), name: 'Nimbit' },
  { _id: ObjectId("52cdef7f4bab8bd67529c6e6"),name: 'OfficialVirtualDJ'},
  { _id: ObjectId("52cdef7c4bab8bd6752980f2"), name: 'OurStage' },
  { _id: ObjectId("52cdef7d4bab8bd675299e42"), name: 'Radionomy' },
  { _id: ObjectId("52cdef7d4bab8bd675299042"), name: 'Rhapsody' },
  { _id: ObjectId("52cdef7c4bab8bd675297d98"), name: 'Slacker' },
  { _id: ObjectId("52cdef7d4bab8bd675299dcd"), name: 'Smule' },
  { _id: ObjectId("52cdef7d4bab8bd67529891b"), name: 'Spotify' },
  { _id: ObjectId("52cdef7f4bab8bd67529be8f"), name: 'Stereomood' },
  { _id: ObjectId("52cdef7c4bab8bd675297f53"), name: 'Thumbplay' },
  { _id: ObjectId("52cdef7c4bab8bd6752981f7"), name: 'blinkbox music' },
  { _id: ObjectId("52cdef7c4bab8bd675297f83"), name: 'imeem' }
]
~~~

In mongoDB capital letters are sorted first and then small letters are sorted. We can change this behaviour using the options. 

## Limiting

~~~js
 db.companies.find({ category_code: "music" }, { name: 1, number_of_employees: 1}).sort({ number_of_empnumber_of_employees: -1}).limit(3);
~~~
Output :
~~~js
[
  {
    _id: ObjectId("52cdef7d4bab8bd67529891b"),
    name: 'Spotify',
    number_of_employees: 5000
  },
  {
    _id: ObjectId("52cdef7d4bab8bd675299042"),
    name: 'Rhapsody',
    number_of_employees: 150
  },
  {
    _id: ObjectId("52cdef7f4bab8bd67529c6e6"),
    name: 'OfficialVirtualDJ',
    number_of_employees: 102
  }
]
~~~