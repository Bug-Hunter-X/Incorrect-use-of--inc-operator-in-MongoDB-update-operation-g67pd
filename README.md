# Incorrect use of $inc operator in MongoDB update operation
This repository demonstrates an example of an uncommon MongoDB bug related to the incorrect use of the `$inc` operator in an update operation.

## Bug Description
The `$inc` operator in MongoDB is used to increment a numerical field by a specified value. However, if the field does not exist, the `$inc` operator will create the field and set its value to the specified increment.

In this example, the code attempts to increment a `counter` field. If the `counter` field does not exist, the code will incorrectly create it and set its value to 1. This can lead to unexpected behavior and data inconsistencies.

## Solution
To address this issue, we need to ensure that the `counter` field exists before attempting to increment it. This can be done using the `$setOnInsert` operator or by checking the existence of the field before performing the update.

## How to reproduce the bug and solution
1. Clone the repository.
2. Run the `bug.js` file to reproduce the bug.
3. Run the `bugSolution.js` file to see how to correctly increment the counter using the $inc operator.

The `bugSolution.js` provides the correct implementation using the `$setOnInsert` operator. By using `$setOnInsert`, we ensure that the counter field is created and initialized to zero before attempting to increment it.