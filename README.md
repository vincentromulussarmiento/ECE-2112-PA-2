# ECE-2112-PA-2
Made by: Vincent Romulus S. Sarmiento | 2ECE-D A.Y.2026-2027

This repository contains the jupyter notebook file for our Programming Assignment 2 in ECE2112, as well as the README file that explains the code more thoroughly.

## Importation of NumPy library
Before starting the programming assignment, the following code has to be ran because it eases the process of making an array, and it contains many useful functions that will definitely ease everyone's coding work.
```Python
import numpy as np
```
## Saving of arrays as a file
The following code is used to save arrays as a file:
```Python
np.save('__________.npy', ___________)
```
The first blank is what you want to name your file with, and the second blank refers to the variable name where you assigned your array to.

## A. Reproducible Normalization Problem
Create a 5x5 array composed of random numbers from 10 to 100 named X, then get the normalized version of said array and store in X_normalized. A normalized array contains values that only ranges from 0 to 1 instead of possibly thousands or more. Lastly, solve for the mean and standard deviation of the normalized array. Display X, X_normalized, its mean and its standard deviation.

Functions(s), Method(s), and/or Operation(s) used:

- np.random.randint(10, 101, size=(5, 5)) - This function produces an array with a 5x5 shape (5 rows and 5 columns) totaling to 25 elements. 10 and 101 means that the array will be filled with numbers between 10 to 100.
- np.random.seed(2112) - This function was used to ensure that everytime the array is printed, it will always produce the same output.
- np.mean() - This is a function that calculates the average of the array. It produces a single number.
- np.std() - This is a function that calculates the standard deviation of the array. Standard deviation basically computes for how spread out your data are. There isn't necessarily a better deviation between a higher or lower result because they imply different things. This function produces a single number.
- str() - This function converts a given data type into a string. This is incredibly useful because in the problem's case, it asks to print the mean and the standard deviation, which is a float. You cannot print a variable that contains an float, so with this function, it converts the float into a string so that it can be printed.

The following formula was given:

X_normalized₁ = (X₁ - Mean of array X) / Standard Deviation of array X

This formula is done to each element of array X which results to a new array that contains normalized values.

Below is the completed code:
```Python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
M = np.mean(X)
S = np.std(X)
X_normalized = (X - M) / S
M_normalized = np.mean(X_normalized)
S_normalized = np.std(X_normalized)
M_str = str(M_normalized)
S_str = str(S_normalized)
```


## B. Cubes divisible by 4 problem
Create a 10x10 array containing the cube of the first 100 integers named C and store every element that is divisible by 4 to array div_by_4 using a boolean condition. Display the shape of C, and array div_by_4 and its size.

Functions(s), Method(s), and/or Operation(s) used:

- (np.arange(1, 101) ** 3) - The .arange() produces an array that follows 3 inputs, the first number is the starting number, the second is the number after your preferred last number since it won't include the number you wrote, in this case we only want 100 so we write 101. You could also include a third number which is the increment, with it, it will only take one number per increment that you put. This whole function is cubed so that every element is cubed.
- .reshape(10,10) - This follows the .arange() function since with it, it will shape the array into 10x10 (10 rows and 10 columns).
- % - This is the modulo operator. When used, it results to a singular number that corresponds to the remainder of the given numbers. For instance, 4 % 2 is zero because when we divide 4 by 2, it is distributed without any excess.
- == - This is the equality operator, this is different from a single equal sign because with that, you are assigning a particular value to a variable, but with this, it checks if your argument is equal to a particular value.
- .shape - This function produces output (a, b, c), where a is the number of rows of the array, b is the number of columns, and c is the depth of the array.
- str() - This function transforms a different data type into a string. It is useful when you need to print an unprintable data type so that you can show the output.
- .size - This function returns a single number, and that is the number of elements of the array.

Below is the completed code:
```Python
C = (np.arange(1, 101) ** 3).reshape(10, 10)
div_by_4 = C[C % 4 == 0]
print("Shape of C:", C.shape)
print("Array div_by_4: \n", div_by_4)
div_by_4_str = str(div_by_4.size)
print("Size of div_by_4:", div_by_4_str)
```


## C. Above-mean squares problem
Create a 6x6 array named S that is composed of the squares of the first 36 positive integers, then solve for the mean of the array, and use a boolean condition to select only the elements larger than the mean and store it in an array named above_mean. Display array S and its mean, and array above_mean and its size.

Functions(s), Method(s), and/or Operation(s) used:

- (np.arange(1, 37) ** 2) - This is a function produces an array that asks for a starting and ending number, and an increment. In this problem's case, the first number is 1 and the second is 37. We input 37 because with the second number, it only counts the number before the input. An increment can also be included but it depends on the problem. This whole function is squared because the problem asks for each element to be squared.
- .reshape(6, 6) - This changes the shape of the produced array into 6x6 (6 rows and 6 columns).
- np.mean() - This calculates for the mathematical average of an array. It results to a single number.
- `>` - This is the greater than operator, it checks if the former is bigger than the latter. If used as an argument, if not met, it will result to that specific block of code to not be executed.
- str() - This converts a different data type into a string.
- .size - This counts the total elements of the array.

Below is the completed code:
```Python
S = (np.arange(1, 37) ** 2).reshape(6, 6)
S_mean = S.mean()
above_mean = S[S > S_mean]
above_mean_str = str(above_mean)
print("Array S: \n", S)
print("Mean of S:", S_mean)
print("Array above_mean: \n", above_mean)
above_mean_str = str(above_mean.size)
print("Size of above_mean:", above_mean_str)
```
