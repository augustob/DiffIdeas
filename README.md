# DiffIdeas
Playing with Diff implementations

This is an experiment about how to compare data (byte arrays) in a more efficient way. 
Given that we have two data chunks to compare, "left" and "right", the solution should return if the data is equal or different. 
The input data is entered in Json.
  
This experiment goes to the basis of data comparison, playing with ideas on how to perform it more efficiently. 

Not being a specialist on this subject, I’m sharing my first insights with this experiment.
There are plenty of ready solutions available on Nuget for comparing and diffing Json data.
This solution doesn’t include any calls or libraries for diffing data. 
This solution presents simple algorithms and a visual representation to the given problem.

## Test 0: The first condition

The first test and costless is the size. 

If the provided data has different sizes no additional tests need to be performed.

The data is encoded and then being test as byte arrays on next steps.

<img src="http://invent4.com/git/image1.JPG" width="800">


## Test 1: The safe and usual approach

Running tests from the start to the end of the data is the most usual way. 

With a loop from the position zero to the length of the data array we have safe results.
The loop breaks if a difference is found.

To consider the data chunks equal the entire array is tested.
The cost of time and processing is directly related with the data size.

The solution performs this test and presents the measures of loop interactions and time cost for the operation.


## Test2: Forward and Backward

This approach tests the data array with two fronts. 
While performing tests form the start to the end a second test is performed from end to the start.
The intention is optimizing the chances of early detection of different data pairs.

Considering data chunks where the differences are at the end part of the array this test will detect this earlier.






