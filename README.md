# PA2_BON-AO
Programming Assignment 2 - Bon-ao, Angelo B. - ECE2112 - 2ECED

After the lecture on Numerical Python, solving the problems for programming assignment two was pretty straight on as the needed syntax and commands were already tackled during the previous lesson.

### 1.
For the first problem, which is the normalization problem, I used the .random.random command for an array to create a 5x5 array with random variables in it. 
For the mean and standard deviation, I individually stored them in a variable as it made coding more readable than straight-up putting the command inside the full equation. 
I stored the mean in 'mean' and stored the standard deviation in 'std_dev'. 

Inputting all the data inside the equation given by the problem, I then stored the data from the normalization equation inside 'Z_X', for it to be denoted as the Z of X or the Normalized array of X. Lastly, I saved the data of 'Z_X' into 'X_normalized.npy'.

### 2.
For the second problem, which is the Divisible by 3 problem, I was initially stuck on how to create an array of integers ranging from 1 to 100 and to make it specifically 10x10. I decided to split the two and tasks and try to do them one at a time. Looking back at the notes from the previous lecture, .arange(l,u,i) is used for collecting the range of numbers, from the lower limit to the upper limit, with the upper limit not included, and an interval splitting the variables in the range.

Using this information, I created an array and inputted the arguments of .arange(1,101,1) to store 1 to 100 integers inside an array. I then used the .resize command to resize the array to be 10x10.
I then squared the array using .square and stored the data into a new variable named 'Squared_A'. Then, to find all the integers divisible by 3, I used the modulo 3 '%3' and equated to 0 to find all the numbers when divided by 3 and leaving no remainder in the 'Squared_A' Array.

The data of the numbers, when divided by 3 and left with no remainder, would then be stored in 'Div_by_3' and eventually saved to 'div_by_3.npy' using .save

