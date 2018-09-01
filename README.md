# DiffIdeas
Playing with Diff implementations

This is an experiment about how to compare data (byte arrays) in a more efficient way.

Given that we have two data chunks to compare, "left" and "right", the solution should return if the data is equal or different. 
The input data is entered as JSON.
  
This experiment goes to the basis of data comparison, playing with ideas and trying to improve the efficiency. 

Not being a specialist on this subject, I’m sharing my first insights with this experiment.
There are plenty of ready solutions available on Nuget for comparing and diffing Json data.
This solution doesn’t include any calls or libraries for diffing data. 
This solution presents simple algorithms and a visual representation to the given problem and suggestions.

## Simple user input/edit

The application presents firstly a simple user interface where the data can be typed, read or edited. There is an option to read Json data from embedded examples.

<img src="http://invent4.com/git/image0.JPG" width="700">


## Test 0: The first condition

The first test is the size. If the provided data has different sizes no additional tests need to be performed.

If data sizes are equal, the data is encoded and then being tested as byte arrays on next steps.

<img src="http://invent4.com/git/image1b.JPG" width="700">


## Test 1: The safe and usual approach

Running tests from the start to the end of the data is the usual way. 

With a loop from the position zero to the length of the data array we have safe results.
The loop breaks if a difference is found. The entire array is tested to consider the data equal. 

The solution performs this test and presents the measures of loop interactions and time cost for the operation.

<img src="http://invent4.com/git/imaget1.JPG" width="700">


## Test 2: Forward and Backward

This approach tests the data array with two fronts. 
While performing tests form the start to the end a second test is performed from end to the start.

The intention is optimizing the chances of early detection of different data pairs.

Considering data chunks where the differences are at the end part of the array this test will detect this earlier. The additional cost of a second comparing must be considered. 

The solution performs this test and presents the measures of loop interactions and time cost for the operation.

<img src="http://invent4.com/git/imaget2.JPG" width="700">


## Test 3: Middle to the edges

This approach uses two testing fronts again but starting on the middle of the data array to the edges.

The intention is testing optimized ways to early detect differences, which will improve solution’s performance.

This third test is performed by the solution and the measures of loop iterations and time are computed.


## Test 4: Hash compare

This test is based on calculating the hash of both data chunks. The hashes are then compared to define equal or not. 

Hashing the files is being performed with XOR and requires the entire data processing for comparison. 

The solution performs this test and compute the measures of loop iterations and time consumed.


## Next Steps

Due to my game development background, the solution was built using Unity3D game engine. This option was made to represent and test my suggestions to the given problem in a visual way.

This is not the appropriated approach for testing large data volumes which would allow best conclusions. 

The next step is convert the algorithms, remove all user interface part, and prepare a REST version of the application allowing big data tests. 

Testing the suggested approaches with bigger data and analyzing the measures of time spent can lead to more important conclusions and insights.


## Conclusions

The different approaches of how comparing the data returned varied results but they are obviously related with where the errors are inside the array (position).

The application on its actual stage don’t allows real great conclusions on the subject.

Performing more complex tests with bigger volume of data is the important stage missing (today) to present useful conclusions.

Understanding the pattern of where errors are often found (according to the data being compared), could make these approaches valid. 

The application can only return EQUAL with safety after testing the entire array of data. Considering this premise true, trying to find the errors earlier is the main suggestion for a performance increase on this type of algorithms.





