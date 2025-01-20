# MongoDB $inc operator type error
This repository demonstrates an example of a common error when using the `$inc` operator in MongoDB update operations. The `$inc` operator is used to increment a numeric field by a specified value, however, providing a string value instead will lead to an error or incorrect results. The solution provides the correct way to increment a numeric field using the `$inc` operator, ensuring that you always pass a numerical value to the operator.

## Bug
The bug is in the incorrect usage of the `$inc` operator in the following code snippet:
```javascript
db.collection.updateOne({"_id":1},{$inc:{ "counter":'1'}})
```
The `counter` field is being incremented by the string value '1' instead of the numerical value 1. This is an incorrect usage of the `$inc` operator and can cause unexpected behavior or errors.

## Solution
The correct way to increment a numeric field using the `$inc` operator is to use a numerical value as the increment.
```javascript
db.collection.updateOne({"_id":1},{$inc:{ "counter":1 }})
```
This code snippet will correctly increment the `counter` field by 1.