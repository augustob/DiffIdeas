# DiffIdeas
Playing with Diff implementations

This is an experiment about how to compare data (byte arrays) in a more efficient way. 
Given that we have two data chunks to compare, <left> and <right>, the solution should return if the data is equal or different. 
The input data is entered in Json.
This experiment goes to the basis of data comparison, playing with ideas on how to perform it more efficiently. 
Not being a specialist on this subject, I’m sharing my first insights with this experiment.
There are plenty of ready solutions available on Nuget for comparing and diffing Json data.
This solution doesn’t include any calls or libraries for diffing data. 
This solution presents simple algorithms and a visual representation to the given problem.

##Test 0: The first condition

The first test and costless is the size. 
If the provided data has different sizes no additional tests need to be performed.
The data is encoded and then being test as byte arrays on next steps.
