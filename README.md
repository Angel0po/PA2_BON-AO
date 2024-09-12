# PA2_BON-AO
Programming Assignment 2 - Bon-ao, Angelo B. - ECE2112 - 2ECED

## Code Solving and Breakdown

After the lecture on Numerical Python, solving the problems for programming assignment two was pretty straightforward as the needed syntax and commands were already tackled during the previous lesson.

### 1.
To start solving the problem, I have to import the library of Numerical Python as numpy onto the code for it to be used. As such
``` python
#Import numerical Python library
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

Using this information, I created an array to create a 5x5 array with purely random elements in it and stored it to the variable X. As seen below,

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

The finished code would look like this
``` python
#Start

#Import numerical python library
import numpy as np

#Store random 5x5 array in X
X = np.array(np.random.random((5,5)))

#Store and Calculate mean and standard deviation 
mean = X.mean()
std_dev = X.std()

#Calculate normalized array
Z_X = (X - mean)/std_dev

#Save normalized array to 'X_normalized.npy'
np.save('X_normalized.npy', Z_X)

#end
```

``` python
#Sample Output

[[ 1.48293407  0.54563574  0.40173804 -0.40444156  0.53172264]
 [-1.33656643  1.39518146  1.28356454  0.22754209 -0.59228945]
 [ 0.77143367 -0.85877205 -0.45229671 -1.24569123 -0.42825375]
 [ 0.33605035  1.42142444 -1.03499808  1.40938648 -1.61559311]
 [ 1.41749808 -0.5516239  -1.03775693 -0.47167949 -1.1941489 ]]
```

### 2.
To start solving the problem, I have to import the library of Numerical Python as numpy onto the code for it to be used. As such
``` python
#Import numerical Python library
import numpy as np 
```
Now, I can start to solve the problem and call numerical Python functions.

For the second problem, which is the Divisible by 3 problem, I was initially stuck on how to create an array of integers ranging from 1 to 100 and to make it specifically 10x10. I decided to split the two tasks and try to do them one at a time. 

Looking back at the notes from the previous lecture, .arange(l,u,i) is used for collecting the range of numbers, from the lower limit to the upper limit, with the upper limit not included, and an interval splitting the variables in the range. The code used as an example during the lecture can be seen below:
``` python
#syntax: np.arange(first:last - interval)
#does not include upper limit

# axis 0 only
z = np.arange(3,7,0.5)
z

#Output
array([3. , 3.5, 4. , 4.5, 5. , 5.5, 6. , 6.5])
```

Using this information, I could create an array, and inside the argument of the array is the command of np.arange of all first one hundred positive integers, which is what I did. It is shown below as to how the code was executed and implemented for the problem.
``` python
#Create array of all first 100 positive integers
A = np.array(np.arange(1,101,1))
```

The stored array in A now has the elements of all the first one hundred integers. Now for the second step, which is for the array to be 10x10. Recalling the lecture, a command of .resize and .reshape was used as seen below
``` python
b.resize(3,2)                        
b

#Sample Output
array([[4, 6],
       [5, 3],
       [2, 1]])

b.reshape(6,1)

#Sample Output
array([[4],
       [6],
       [5],
       [3],
       [2],
       [1]])
```

Researching more about the two commands, I found that the biggest difference between them is that .reshape(m,n) can only change the shape and not modify the number of elements to form the shape it is tasked to create. On the other hand, .resize(m,n) can add or remove the number of elements within an array to force it to become the inputted size. In this problem, both commands can be used as there are enough elements to use .reshape and .resize for the elements not to be modified. I chose to use resize to make sure the array was resized to a 10x10 array.

``` python
#Resize array to be 10 x 10
A.resize(10,10)

#Supposed Output (NOT INCLUDED IN FINAL OUTPUT)
print(A)
[[  1   2   3   4   5   6   7   8   9  10]
 [ 11  12  13  14  15  16  17  18  19  20]
 [ 21  22  23  24  25  26  27  28  29  30]
 [ 31  32  33  34  35  36  37  38  39  40]
 [ 41  42  43  44  45  46  47  48  49  50]
 [ 51  52  53  54  55  56  57  58  59  60]
 [ 61  62  63  64  65  66  67  68  69  70]
 [ 71  72  73  74  75  76  77  78  79  80]
 [ 81  82  83  84  85  86  87  88  89  90]
 [ 91  92  93  94  95  96  97  98  99 100]]
```

The next step is to square all the elements by itself. I found a command through the internet that squares all the elements by itself inside an array and used it, as seen below;
``` python
#Stores a new array that squared every element by itself
Squared_A = np.square(A)

#Supposed Output (NOT INCLUDED IN FINAL OUTPUT)
print(Squared_A)
[[    1     4     9    16    25    36    49    64    81   100]
 [  121   144   169   196   225   256   289   324   361   400]
 [  441   484   529   576   625   676   729   784   841   900]
 [  961  1024  1089  1156  1225  1296  1369  1444  1521  1600]
 [ 1681  1764  1849  1936  2025  2116  2209  2304  2401  2500]
 [ 2601  2704  2809  2916  3025  3136  3249  3364  3481  3600]
 [ 3721  3844  3969  4096  4225  4356  4489  4624  4761  4900]
 [ 5041  5184  5329  5476  5625  5776  5929  6084  6241  6400]
 [ 6561  6724  6889  7056  7225  7396  7569  7744  7921  8100]
 [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]
```

I stored the new array of the squared elements to 'Squared_A'.  Then, to find all the integers divisible by 3, I used the modulo 3 '%3' and equated it to 0 to be the condition. I then stored the new array of elements divisible by 3 in 'Div_by_3'. The code executed can be seen below;
``` python
#Stores every element from Squared_A that is divisible by 3
Div_by_3 = Squared_A[A%3==0]

#Supposed Output (NOT INCLUDED IN FINAL OUTPUT)
print(Div_by_3)
[   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
```

The last step of the solution to problem two is to save the array of 'Div_by_3'  as 'div_by_3.npy'. Using .save again, the code can be seen below;
``` python
#Save array with elements divisble by 3 to 'div_by_3.npy'
np.save('div_by_3.npy',Div_by_3)
```

The finished code would look like this
``` python
#start

#Import numerical python library
import numpy as np

#Create array of all first 100 positive integers
A = np.array(np.arange(1,101,1))
print(A)
#Resize array to be 10 x 10
A.resize(10,10)
print(A)
#Stores a new array that squared every element by itself
Squared_A = np.square(A)

#Stores every element from Squared_A that is divisible by 3
Div_by_3 = Squared_A[A%3==0]
print(Div_by_3)
#Save array with elements divisble by 3 to 'div_by_3.npy'
np.save('div_by_3.npy',Div_by_3)

#end
```

``` python
#Sample Output
[   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
```

[   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
```

