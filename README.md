# PA2_BON-AO
Programming Assignment 2 - Bon-ao, Angelo B. - ECE2112 - 2ECED

After the lecture on Numerical Python, solving the problems for programming assignment two was pretty straightforward as the needed syntax and commands were already tackled during the previous lesson.

### 1.
To start solving the problem, I have to import the library of Numerical Python as numpy onto the code for it to be used. As such
``` python
#Import numerical python library
import numpy as np 
```
Now, I can start to solve the problem and call numerical Python functions.
For the first problem, the normalization problem, the first step is creating a random array. Recalling back to the lecture, a command was taught how to create an array of purely randomized elements in them, as seen below; 
``` python
#np.random.random((m,n))
np.random.random((2,3))

#Sample Output
array([[0.41993434, 0.04122826, 0.8373043 ],
       [0.50643017, 0.78434918, 0.38655454]])
```

Using this information, I created an array to create a 5x5 array with the purely random elements in it and storing it to the variable X. As seen below,

``` python
#Store random 5x5 array in X
X = np.array(np.random.random((5,5)))
```

I immediately placed the np.random.random command inside the command of the np.array for it to automatically create and store a random 5x5 array into the variable X.
I understand that every time the code is to be run, the end result will always be different as .random.random always randomize the elements inside every time the code is run.

For the mean and standard deviation, I individually stored them in a variable as it made coding more readable than straight-up putting the command inside the full equation. As seen below, using the .mean() and .std() call  provided by the problem and placing the variable X
``` python
#Store and Calculate mean and standard deviation 
mean = X.mean()
std_dev = X.std()
```
I stored the mean in 'mean' and stored the standard deviation in 'std_dev'. This is much more readable for me as it indicates that the mean and standard deviation are now saved onto a variable and can be used in other equations if need be, but for this problem, only normalization is required. I traded off the length of the code to make it look cleaner.

Inputting all the data inside the equation given by the problem, I then calculated the normalized X by putting it into the equation given by the problem using the array X, the calculated mean, and std_dev. The result of the equation will be stored on to Z_X so that it can be saved to a file
``` python
#Calculate normalized array
Z_X = (X - mean)/std_dev
```

Finally, the last step for the problem. I recalled a command used during the lecture which was np.load as seen below, I figured as much that there should be an equivalent save command that saves an array which turned out to be np.save.
``` python
#viewing the contents on a numpy file
#syntax - np.load('filename.py')
data = np.load('epk.npy')
data
```

And for saving the normalized array to 'X_normalized.npy', the code executed is as follows. Finishing the solution to the first problem.
``` python
#Save normalized array to 'X_normalized.npy'
np.save('X_normalized.npy', Z_X)
```

### 2.
To start solving the problem, I have to import the library of Numerical Python as numpy onto the code for it to be used. As such
``` python
#Import numerical python library
import numpy as np 
```
Now, I can start to solve the problem and call numerical Python functions.

For the second problem, which is the Divisible by 3 problem, I was initially stuck on how to create an array of integers ranging from 1 to 100 and to make it specifically 10x10. I decided to split the two tasks and try to do them one at a time. 

Looking back at the notes from the previous lecture, .arange(l,u,i) is used for collecting the range of numbers, from the lower limit to the upper limit, with the upper limit not included, and an interval splitting the variables in the range. The code used as en example during the lecture can be seen below:
``` python
#syntax: np.arange(first:last - interval)
#does not include upper limit

# axis 0 only
z = np.arange(3,7,0.5)
z

#Output
array([3. , 3.5, 4. , 4.5, 5. , 5.5, 6. , 6.5])
```

Using this information, I could create an array, and inside the argument of the array is the command of np.range of all first one hundred positive integers, which is what I did. It is shown below as to how the code was executed and implemented for the problem.
``` python
#Create array of all first 100 positive integers
A = np.array(np.arange(1,101,1))
```

The stored array in A now has the elements of all the first one hundred integers. Recakking

Using this information, I created an array and inputted the arguments of .arange(1,101,1) to store 1 to 100 integers inside an array. I then used the .resize command to resize the array to be 10x10.
I then squared the array using .square and stored the data into a new variable named 'Squared_A'. Then, to find all the integers divisible by 3, I used the modulo 3 '%3' and equated to 0 to find all the numbers when divided by 3 and leaving no remainder in the 'Squared_A' Array.

The data of the numbers, when divided by 3 and left with no remainder, would then be stored in 'Div_by_3' and eventually saved to 'div_by_3.npy' using .save

