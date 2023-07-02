# **Projection: Returning Specific Data from a Query in MongoDB**

~~~js
use sample_training;
~~~

~~~js
db.inspections.findOne();
~~~
Output :
~~~js
{
  _id: ObjectId("56d61033a378eccde8a8354f"),
  id: '10021-2015-ENFO',
  certificate_number: 9278806,
  business_name: 'ATLIXCO DELI GROCERY INC.',
  date: 'Feb 20 2015',
  result: 'No Violation Issued',
  sector: 'Cigarette Retail Dealer - 127',
  address: { city: 'RIDGEWOOD', zip: 11385, street: 'MENAHAN ST', number: 1712 }
}
~~~

~~~js
db.inspections.find({sector: "Restaurant - 818"});
~~~
Output :
~~~js
[
  {
    _id: ObjectId("56d61033a378eccde8a83697"),
    id: '21501-2015-ENFO',
    certificate_number: 8660002,
    business_name: 'Sbarro Queens Crossing, LLC',
    date: 'Apr 28 2015',
    result: 'NOH Withdrawn',
    sector: 'Restaurant - 818',
    address: {
      city: 'MELVILLE',
      zip: 11747,
      street: 'BROADHOLLOW RD',
      number: 401
    }
  },
  {
    _id: ObjectId("56d61033a378eccde8a8402d"),
    id: '8830-2015-CMPL',
    certificate_number: 9313570,
    business_name: 'OCEAN AVENUE BAGEL BOY LLC',
    date: 'Oct 27 2015',
    result: 'No Violation Issued',
    sector: 'Restaurant - 818',
    address: { city: 'BROOKLYN', zip: 11235, street: 'E 16TH ST', number: 2601 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84127"),
    id: '49502-2015-ENFO',
    certificate_number: 3043375,
    business_name: 'PEKING OISHI 88 INC',
    date: 'Aug 28 2015',
    result: 'Pass',
    sector: 'Restaurant - 818',
    address: {
      city: 'BROOKLYN',
      zip: 11216,
      street: 'FULTON ST',
      number: '1563B'
    }
  },
  {
    _id: ObjectId("56d61033a378eccde8a841f0"),
    id: '20579-2014-CMPL',
    certificate_number: 9303241,
    business_name: 'AZURI CAFE',
    date: 'May  6 2015',
    result: 'No Violation Issued',
    sector: 'Restaurant - 818',
    address: { city: 'NEW YORK', zip: 10019, street: 'W 51ST ST', number: 465 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a8437a"),
    id: '22306-2014-CMPL',
    certificate_number: 9283572,
    business_name: 'MESQUITES VERDES CORP',
    date: 'Feb  2 2015',
    result: 'No Violation Issued',
    sector: 'Restaurant - 818',
    address: { city: 'BRONX', zip: 10457, street: 'E TREMONT AVE', number: 515 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a8438a"),
    id: '49364-2015-ENFO',
    certificate_number: 9309339,
    business_name: 'SCREENING ROOM BAR LLC',
    date: 'Aug 26 2015',
    result: 'No Violation Issued',
    sector: 'Restaurant - 818',
    address: { city: 'ASTORIA', zip: 11106, street: '32ND ST', number: 3455 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a843d2"),
    id: '61621-2015-ENFO',
    certificate_number: 9319752,
    business_name: 'Nostrand Ice Cream Store Inc',
    date: 'Oct 27 2015',
    result: 'No Violation Issued',
    sector: 'Restaurant - 818',
    address: {
      city: 'BROOKLYN',
      zip: 11235,
      street: 'NOSTRAND AVE',
      number: 3824
    }
  },
  {
    _id: ObjectId("56d61033a378eccde8a845fd"),
    id: '46341-2015-ENFO',
    certificate_number: 3043244,
    business_name: "CRESCENT GARDEN KING'S INC.",
    date: 'Aug  6 2015',
    result: 'Pass',
    sector: 'Restaurant - 818',
    address: { city: 'BROOKLYN', zip: 11223, street: '86TH ST', number: 2637 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84659"),
    id: '54426-2015-ENFO',
    certificate_number: 9306554,
    business_name: 'Landmark Tavern',
    date: 'Sep 30 2015',
    result: 'No Violation Issued',
    sector: 'Restaurant - 818',
    address: { city: 'NEW YORK', zip: 10036, street: '11TH AVE', number: 626 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84735"),
    id: '56837-2015-ENFO',
    certificate_number: 3044357,
    business_name: 'BB #1 PIZZA CORPORATION',
    date: 'Oct  1 2015',
    result: 'Pass',
    sector: 'Restaurant - 818',
    address: {
      city: 'NEW YORK',
      zip: 10025,
      street: 'AMSTERDAM AVE',
      number: 854
    }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84849"),
    id: '42663-2015-ENFO',
    certificate_number: 3042933,
    business_name: 'TOYOTA CUISINE',
    date: 'Jul 22 2015',
    result: 'Fail',
    sector: 'Restaurant - 818',
    address: { city: 'BROOKLYN', zip: 11220, street: '7TH AVE', number: 6001 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a849b4"),
    id: '16126-2014-CMPL',
    certificate_number: 9301618,
    business_name: 'MARGOT PATISSERIE',
    date: 'Jan 28 2015',
    result: 'Out of Business',
    sector: 'Restaurant - 818',
    address: { city: 'NEW YORK', zip: 10023, street: 'BROADWAY', number: 2109 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84a2b"),
    id: '13664-2015-ENFO',
    certificate_number: 3019769,
    business_name: '372 MARKET INC.',
    date: 'Mar 20 2015',
    result: 'Pass',
    sector: 'Restaurant - 818',
    address: {
      city: 'BROOKLYN',
      zip: 11238,
      street: 'LAFAYETTE AVE',
      number: 372
    }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84a41"),
    id: '50809-2015-ENFO',
    certificate_number: 9309010,
    business_name: '35-01 36TH STREET REST., INC.',
    date: 'Sep  2 2015',
    result: 'No Violation Issued',
    sector: 'Restaurant - 818',
    address: { city: 'ASTORIA', zip: 11106, street: '36TH ST', number: 3501 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84a50"),
    id: '17662-2015-CMPL',
    certificate_number: 9319155,
    business_name: 'NYC Fried Chicken',
    date: 'Jan  4 2016',
    result: 'No Violation Issued',
    sector: 'Restaurant - 818',
    address: { city: 'NEW YORK', zip: 10018, street: 'W 39TH ST', number: 270 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84aa6"),
    id: '41361-2015-ENFO',
    certificate_number: 9312972,
    business_name: 'NANIWA JAPANESE RESTAURANT INC',
    date: 'Jul 15 2015',
    result: 'Warning',
    sector: 'Restaurant - 818',
    address: { city: 'BROOKLYN', zip: 11223, street: 'KINGS HWY', number: 276 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84bb9"),
    id: '40399-2015-ENFO',
    certificate_number: 3046867,
    business_name: 'PRIMAVERA CAFE CORP',
    date: 'Aug  6 2015',
    result: 'Pass',
    sector: 'Restaurant - 818',
    address: { city: 'BRONX', zip: 10458, street: 'E FORDHAM RD', number: 387 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84c63"),
    id: '68592-2015-ENFO',
    certificate_number: 9320881,
    business_name: 'RICHARD CHOU, INC',
    date: 'Dec  4 2015',
    result: 'No Violation Issued',
    sector: 'Restaurant - 818',
    address: {
      city: 'BROOKLYN',
      zip: 11229,
      street: 'NOSTRAND AVE',
      number: 3594
    }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84d2a"),
    id: '41321-2015-ENFO',
    certificate_number: 9312983,
    business_name: 'FUJI HANA RESTAURANT INC',
    date: 'Jul 17 2015',
    result: 'Warning',
    sector: 'Restaurant - 818',
    address: { city: 'BROOKLYN', zip: 11223, street: 'AVENUE U', number: 512 }
  },
  {
    _id: ObjectId("56d61033a378eccde8a84ddb"),
    id: '41351-2015-ENFO',
    certificate_number: 9312970,
    business_name: 'KINGS HIGHWAY GREAT WALL INC',
    date: 'Jul 15 2015',
    result: 'Warning',
    sector: 'Restaurant - 818',
    address: { city: 'BROOKLYN', zip: 11223, street: 'KINGS HWY', number: 284 }
  }
]
Type "it" for more
~~~

~~~js
db.inspections.find({sector: "Restaurant - 818"}, { business_name: 1, result: 1});
~~~
Output :
~~~js
[
  {
    _id: ObjectId("56d61033a378eccde8a83697"),
    business_name: 'Sbarro Queens Crossing, LLC',
    result: 'NOH Withdrawn'
  },
  {
    _id: ObjectId("56d61033a378eccde8a8402d"),
    business_name: 'OCEAN AVENUE BAGEL BOY LLC',
    result: 'No Violation Issued'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84127"),
    business_name: 'PEKING OISHI 88 INC',
    result: 'Pass'
  },
  {
    _id: ObjectId("56d61033a378eccde8a841f0"),
    business_name: 'AZURI CAFE',
    result: 'No Violation Issued'
  },
  {
    _id: ObjectId("56d61033a378eccde8a8437a"),
    business_name: 'MESQUITES VERDES CORP',
    result: 'No Violation Issued'
  },
  {
    _id: ObjectId("56d61033a378eccde8a8438a"),
    business_name: 'SCREENING ROOM BAR LLC',
    result: 'No Violation Issued'
  },
  {
    _id: ObjectId("56d61033a378eccde8a843d2"),
    business_name: 'Nostrand Ice Cream Store Inc',
    result: 'No Violation Issued'
  },
  {
    _id: ObjectId("56d61033a378eccde8a845fd"),
    business_name: "CRESCENT GARDEN KING'S INC.",
    result: 'Pass'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84659"),
    business_name: 'Landmark Tavern',
    result: 'No Violation Issued'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84735"),
    business_name: 'BB #1 PIZZA CORPORATION',
    result: 'Pass'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84849"),
    business_name: 'TOYOTA CUISINE',
    result: 'Fail'
  },
  {
    _id: ObjectId("56d61033a378eccde8a849b4"),
    business_name: 'MARGOT PATISSERIE',
    result: 'Out of Business'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84a2b"),
    business_name: '372 MARKET INC.',
    result: 'Pass'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84a41"),
    business_name: '35-01 36TH STREET REST., INC.',
    result: 'No Violation Issued'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84a50"),
    business_name: 'NYC Fried Chicken',
    result: 'No Violation Issued'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84aa6"),
    business_name: 'NANIWA JAPANESE RESTAURANT INC',
    result: 'Warning'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84bb9"),
    business_name: 'PRIMAVERA CAFE CORP',
    result: 'Pass'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84c63"),
    business_name: 'RICHARD CHOU, INC',
    result: 'No Violation Issued'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84d2a"),
    business_name: 'FUJI HANA RESTAURANT INC',
    result: 'Warning'
  },
  {
    _id: ObjectId("56d61033a378eccde8a84ddb"),
    business_name: 'KINGS HIGHWAY GREAT WALL INC',
    result: 'Warning'
  }
]
Type "it" for more
~~~

~~~js
db.inspections.find({sector: "Restaurant - 818"}, { business_name: 1, result: 1, _id: 0 });
~~~
Output :
~~~js
[
  { business_name: 'Sbarro Queens Crossing, LLC', result: 'NOH Withdrawn' },
  { business_name: 'OCEAN AVENUE BAGEL BOY LLC', result: 'No Violation Issued' },
  { business_name: 'PEKING OISHI 88 INC', result: 'Pass' },
  { business_name: 'AZURI CAFE', result: 'No Violation Issued' },
  { business_name: 'MESQUITES VERDES CORP', result: 'No Violation Issued' },
  { business_name: 'SCREENING ROOM BAR LLC', result: 'No Violation Issued' },
  { business_name: 'Nostrand Ice Cream Store Inc', result: 'No Violation Issued' },
  { business_name: "CRESCENT GARDEN KING'S INC.", result: 'Pass' },
  { business_name: 'Landmark Tavern', result: 'No Violation Issued' },
  { business_name: 'BB #1 PIZZA CORPORATION', result: 'Pass' },
  { business_name: 'TOYOTA CUISINE', result: 'Fail' },
  { business_name: 'MARGOT PATISSERIE', result: 'Out of Business' },
  { business_name: '372 MARKET INC.', result: 'Pass' },
  { business_name: '35-01 36TH STREET REST., INC.', result: 'No Violation Issued' },
  { business_name: 'NYC Fried Chicken', result: 'No Violation Issued' },
  { business_name: 'NANIWA JAPANESE RESTAURANT INC', result: 'Warning' },
  { business_name: 'PRIMAVERA CAFE CORP', result: 'Pass' },
  { business_name: 'RICHARD CHOU, INC', result: 'No Violation Issued' },
  { business_name: 'FUJI HANA RESTAURANT INC', result: 'Warning' },
  { business_name: 'KINGS HIGHWAY GREAT WALL INC', result: 'Warning' }
]
Type "it" for more
~~~

Inclusion and exclusion statements can not be combined in projection i.e either we can set fields' value to 0 or to 1 but not both. _id is a special field with exception.

