# **Aggregation Pipeline Operators**

[Complete Aggregation Pipeline Operators](https://www.mongodb.com/docs/manual/reference/operator/aggregation/)

## **```$abs```**
Returns the absolute value of a number.

~~~js
{ $abs: <number> }
~~~
or
~~~js
{ $abs: <expr> }
~~~

~~~js
{ _id: 1, start: 5, end: 8 }
{ _id: 2, start: 4, end: 4 }
{ _id: 3, start: 9, end: 7 }
{ _id: 4, start: 6, end: 7 }
~~~

~~~js
db.ratings.aggregate([
   {
     $project: { delta: { $abs: { $subtract: [ "$start", "$end" ] } } }
   }
])
~~~

## **```$add```, ```$multiply```, ```$max```, ```$min``` and ```$avg```**

~~~js
{ $add: [ <expression1>, <expression2>, ... ] }
~~~

~~~js
{ $multiply: [ <expression1>, <expression2>, ... ] }
~~~

~~~js
{ $max: [ <expression1>, <expression2>, ... ] }
~~~

~~~js
{ $min: [ <expression1>, <expression2>, ... ] }
~~~

~~~js
{ $avg: [ <expression1>, <expression2>, ... ] }
~~~

### **Use in $group Stage**

Data
~~~js
{ "_id" : 1, "item" : "abc", "price" : 10, "quantity" : 2, "date" : ISODate("2014-01-01T08:00:00Z") }
{ "_id" : 2, "item" : "jkl", "price" : 20, "quantity" : 1, "date" : ISODate("2014-02-03T09:00:00Z") }
{ "_id" : 3, "item" : "xyz", "price" : 5, "quantity" : 5, "date" : ISODate("2014-02-03T09:05:00Z") }
{ "_id" : 4, "item" : "abc", "price" : 10, "quantity" : 10, "date" : ISODate("2014-02-15T08:00:00Z") }
{ "_id" : 5, "item" : "xyz", "price" : 5, "quantity" : 10, "date" : ISODate("2014-02-15T09:12:00Z") }
~~~

~~~js
db.sales.aggregate(
   [
     {
       $group:
         {
           _id: "$item",
           avgAmount: { $avg: { $multiply: [ "$price", "$quantity" ] } },
           avgQuantity: { $avg: "$quantity" }
         }
     }
   ]
)
~~~

Output

~~~js
{ "_id" : "xyz", "avgAmount" : 37.5, "avgQuantity" : 7.5 }
{ "_id" : "jkl", "avgAmount" : 20, "avgQuantity" : 1 }
{ "_id" : "abc", "avgAmount" : 60, "avgQuantity" : 6 }
~~~



### **Use in $project Stage**

~~~js
{ "_id": 1, "quizzes": [ 10, 6, 7 ], "labs": [ 5, 8 ], "final": 80, "midterm": 75 }
{ "_id": 2, "quizzes": [ 9, 10 ], "labs": [ 8, 8 ], "final": 95, "midterm": 80 }
{ "_id": 3, "quizzes": [ 4, 5, 5 ], "labs": [ 6, 5 ], "final": 78, "midterm": 70 }
~~~

~~~js
db.students.aggregate([
   { $project: { quizAvg: { $avg: "$quizzes"}, labAvg: { $avg: "$labs" }, examAvg: { $avg: [ "$final", "$midterm" ] } } }
])
~~~

~~~js
{ "_id" : 1, "quizAvg" : 7.666666666666667, "labAvg" : 6.5, "examAvg" : 77.5 }
{ "_id" : 2, "quizAvg" : 9.5, "labAvg" : 8, "examAvg" : 87.5 }
{ "_id" : 3, "quizAvg" : 4.666666666666667, "labAvg" : 5.5, "examAvg" : 74 }
~~~

## **```$ceil```, ```$floor```, ```$round``` and ```$sqrt```**


~~~js
{ $ceil: <number> }
~~~

~~~js
{ $floor: <number> }
~~~

~~~js
{ $sqrt: <number> }
~~~

{ $round : [ <number>, <place> ] }


## **```$count```**

~~~js
{ $count: { } }
~~~

It does not accept any parameters.

## **```$divide```,  and ```$substract```**

~~~js
{ $divide: [ <expression1>, <expression2> ] }
~~~

~~~js
{ $mod: [ <expression1>, <expression2> ] }
~~~

~~~js
{ $substract: [ <expression1>, <expression2> ] }
~~~




## **```$cmp```**

## **```$cond```**
