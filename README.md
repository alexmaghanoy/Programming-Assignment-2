# Programming Assignment 2

## Problem 1: Normalization Problem

Normalization is a fundamental preprocessing technique in data analytics that involves two main steps:

1. **Centering** :  Subtracting the mean of the data.
2. **Scaling** :  Dividing by the standard deviation of the data.

This process helps to standardize the data, making it easier to analyze or input into machine learning models. Mathematically, normalization can be expressed as:

`Z = (𝑋−x̄) / 𝜎`

*where:*
- *X*  is the original data,
- *x̄* is the mean of the data,
- *𝜎* is the standard deviation of the data.

#### Task:
- Create a random 5 x 5 NumPy array and store it in a variable `X`.
- Normalize the array `X` by centering and scaling it.
- Save the normalized array to a file named `X_normalized.npy`.

#### Example:
To help understand the process, consider the following example:
- If `X = [1, 2, 3, 4, 5]`, then the mean x̄ = `3.0` and standard deviation 𝜎 = `1.4142135623730951`.
- The normalized values *Z* would be `[-1.41421356 -0.70710678  0.  0.70710678  1.41421356]`.

#### Expected Output:
- The normalized array should have a mean of approximately 0 and a standard deviation of 1.

Use Python's `.mean()` and `.std()` functions to calculate the mean and standard deviation element-wise.



### CODE ###
    
  `import numpy as np`    *// import the numpy library //*

  `X = np.random.random((5,5))`    *// generate random values for a 5x5 array //*
    
  `mean = X.mean()`     *// calculate the mean of array X //*
  
  `std = X.std()`     *// calculate the standard deviation of array X //*
    
  `Z = (X - mean)/std`     *// normalize array X by inputting the data above //*

  `np.save('X_normalized.npy', X)`     *// save array X to a file named "X_normalized.npy" //*
    
  `data = np.load('X_normalized.npy')`     *// load the saved array file //*
  
  `data`


## Problem 2: Divisible by 3 Problem

In this problem, you will create a 10 x 10 NumPy array `A` that contains the squares of the first 100 positive integers.

#### Task:
1. Create a 10 x 10 ndarray `A` such that:
   - The first row contains the squares of the integers from 1 to 10.
   - The second row contains the squares of the integers from 11 to 20, and so on.
   
2. Find all elements in this ndarray that are divisible by 3.
3. Save the resulting array to a file named `div_by_3.npy`.

#### Example:
               A = 
     [1    4    ⋯   81    100
      ⋮     ⋮    ⋱    ⋮      ⋮
      ⋮     ⋮    ⋱    ⋮      ⋮ 
      ⋮     ⋮    ⋱    ⋮      ⋮
    8281  8464  ⋯  9801  10000]


#### Finding Elements Divisible by 3:
- To determine which elements are divisible by 3, you can use the modulus operator `%` in Python.
- For example, if `A = [1, 4, 9, 16]`, elements divisible by 3 are `[9]`.

#### Expected Output:
- A 1D array of elements from `A` that are divisible by 3, saved as `div_by_3.npy`.



### CODE ###

 `import numpy as np`     *// import the numpy library //*

 `A = np.arange(1,101).reshape(10,10)**2`     
 *// create a 10x10 array with the squares of the first 100 positive integers //*
    
 `Y = A[A % 3 == 0]`     *// determine if the element is divisible by 3 //*

 `np.save('div_by_3.npy', Y)`     *// save array Y to a file named "div_by_3.npy" //*

 `data = np.load('div_by_3.npy')`     *// load the saved array file //*    
 `data`
    
