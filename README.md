# ECE-2112-PA-2
### **Made by: Evan James G. Paciencia|2ECE-C**
This repository contains Programming Assignment 2 for the course "Advanced Computer Programming" of S.Y. 2026-2027. This assignment covers three problems of NUMERICAL PYTHON (NUMPY) of about Module 2 - Numpy
## A. REPRODUCIBLE NORMALIZATION PROBLEM
Create a reproducible random 5×5 integer array named X. Use the following two statements before
performing any calculation:
```
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
```
Normalize the complete array using
```math
Z = \frac{x - \bar{x}}{\sigma}
```

<br>where $\bar{x}$ is the mean of all 25 elements, and $\sigma$ is their population standard deviation as returned by
NumPy’s default std() call. Store the normalized array in X normalized. <br>
<br>The following functions and methods were used:<br>
``random.seed()`` - Sets the starting point for generating random numbers, allowing the same random results to be reproduced <br>
``random.randint()`` - Generates a random integer within a range <br>
``.divide(a,b)`` - Divides a by b <br>
``.subtract(a,b)`` - Subtracts a by b <br>
``.mean()`` - Gets the mean of a variable <br>
``.std`` - Gets the Standard Deviation of a variable <br>
<br>These built-in functions and methods were then combined to produce a Python code that meets the requirements: Display X, X normalized, its mean, and its standard deviation. Up to floating-point rounding, the normalized mean must be 0, and the normalized standard deviation must be 1.<br>
<br>
```
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
np.save("X_normalized",np.divide(np.subtract(X,X.mean()),np.std(X)))
print("X:\n",X,"\nX_Normalized:\n",np.load('X_normalized.npy'),"\nMean:",X.mean(),"\nStandard Deviation:",np.std(X))
print("X_normalized mean:",(np.load('X_normalized.npy')).mean())
print("X_normalized std:",(np.load('X_normalized.npy')).std())
```


## B. CUBES DIVISIBLE BY 4 PROBLEM
Create the first 100 positive integers, cube every element, and reshape the result into a 10 × 10 array named C. Thus, C begins with 1<sup>3</sup> and ends with 100<sup>3</sup>. Use a Boolean condition on C to obtain every cubed value divisible by 4. Store the selected values in
div_by_4. Preserve NumPy’s normal row-major selection order.<br>
<br>The following functions and methods were used:<br>
``.arange(a,b,c)`` - Creates an array of evenly spaced values of c starting from a, to b, excluding the final value <br>
``c.reshape(a,b)`` - Reshapes array c into a(row) x b(colume) <br>
``a%b`` - Gets the remainder by dividing a by b<br>
``a**b`` - Raises a by b number of times<br>
<br>These built-in functions and methods were then combined to produce a Python code that meets the requirements: Display the shape of C, the array div_by_4, and the number of selected elements. A correct solution has 50 selected elements; the first is 8, and the last is 1,000,000.<br><br>
```
C=np.arange(1,101,1)**3
C.reshape(10,10)
div_by_4=C[C%4==0]
np.save('div_by_4',div_by_4)
print("\nCubed first 100 integers (in 10x10):\n",C,"\nDivisble by 4: ",div_by_4)
```


## C. ABOVE-MEAN SQUARES PROBLEM
Create a 6 × 6 array named S containing the squares of the first 36 positive integers in increasing row-major order. Compute the mean of all elements of S and store it in S_mean. Then use Boolean filtering to select only the elements strictly greater than S_mean. Store these values in above_mean.<br>
<br>The following functions and methods were used:<br>
``.arange(a,b,c)`` - Creates an array of evenly spaced values of c starting from a, to b, excluding the final value<br>
``c.reshape(a,b)`` - Reshapes array c into a(row) x b(colume)<br>
``.mean()`` - Calculates the average of the array <br>
``S[S>2]`` - Selects all the values of S when the statement/operation is true <br>
<br>These built-in functions and methods were then combined to produce a Python code that meets the requirements: Display S, S mean, above mean, and the number of selected elements. A correct solution has 15 selected elements; the first is 484 and the last is 1296.<br><br>
```
S=np.arange(1,37,1)**2
S.reshape(6,6)
S_mean=S.mean()
Above_mean=S[S>S_mean]
np.save('above_mean',Above_mean)
print("S: \n",S,"\nS_Mean: \n",S_mean,"\nAbove Mean: \n",Above_mean)
```
# Edit/History Log
Created: 9/2/2026
<br>Last edited: 9/3/2026
<br>Changes: <br>
Updated 2ECEC_Paciencia_PA2.ipynv
