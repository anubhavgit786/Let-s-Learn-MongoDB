# **Element Query Operators**

Element operators return data based on field existence or data types.

1. ```$exists```
2. ```$type```

## **```$exists``` Operator**

Syntax:

~~~js
{ field: { $exists: <boolean> } }
~~~

When <boolean> is true, ```$exists``` matches the documents that contain the field, including documents where the field value is null. If <boolean> is false, the query returns only the documents that do not contain the field.

MongoDB ```$exists``` does not correspond to SQL operator exists. For SQL exists, refer to the ```$in``` operator.

## **BSON Types**

| Type    | Number | Alias | Notes |
| :--------: | :-------: | :-------: | :-------: |
| Double | 1 | "double" |
| String | 2 | "string" | 
| Object | 3 | "object" |
| Array | 4 | "array" |
| Binary Data | 5 | "binData" |
| Undefined | 6 | "undefined" | Deprecated |
| ObjectId | 7 | "objectId" |
| Boolean | 8 | "bool" |
| Date | 9 | "date" |
| Null | 10 | "null" |
| Regular Expression | 11 | "regex" |
| DBPointer | 12 | "dbPointer" | Deprecated |
| JavaScript | 13 | "javascript" |
| Symbol | 14 | "symbol" | Deprecated |
| JavaScript code with scope | 15 | "javascriptWithScope" | Deprecated |
| 32-bit integer | 16 | "int" |
| Timestamp | 17 | "timestamp" |
| 64-bit integer | 18 | "long" |
| Decimal128 | 19 | "decimal" |
| Min Key | -1 | "minKey" |
| Max Key | 127 | "maxKey" |


## **```$type``` Operator**

```$type``` selects documents where the value of the field is an instance of the specified BSON type(s). Querying by data type is useful when dealing with highly unstructured data where data types are not predictable.

A ```$type``` expression for a single BSON type has the following syntax:

~~~js
{ field: { $type: <BSON type> } }
~~~

You can specify either the number or alias for the 
BSON type

The ```$type``` expression can also accept an array of BSON types and has the following syntax:

~~~js
{ field: { $type: [ <BSON type1> , <BSON type2>, ... ] } }
~~~

The above query will match documents where the field value is any of the listed types. The types specified in the array can be either numeric or string aliases.