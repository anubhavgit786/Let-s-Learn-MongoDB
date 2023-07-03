# **Field Update Operators**

## **```$min``` and ```$max```**

The $min updates the value of the field to a specified value if the specified value is less than the current value of the field.
The $max updates the value of the field to a specified value if the specified value is greater than the current value of the field.

~~~js
{ $max: { <field1>: <value1>, ... } }
~~~

~~~js
{ $min: { <field1>: <value1>, ... } }
~~~


## **```$mul```,  ```$inc```, ```$rename``` and ```$set```**

~~~js
{ $mul: { <field1>: <value1>, ... } }
~~~

~~~js
{ $inc: { <field1>: <value1>, ... } }
~~~

~~~js
{$rename: { <field1>: <newName1>, <field2>: <newName2>, ... } }
~~~

~~~js
{ $set: { <field1>: <value1>, ... } }
~~~

## **```$unset```**

It deletes a particular field.

~~~js
{ $unset: { <field1>: "", ... } }
~~~

