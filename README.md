# Programming Assignment 2

----- NORMALIZATION PROBLEM -----

Normalization is one of the most basic preprocessing techniques in data analytics. This involves centering and scaling process. 
Centering means subtracting the data from the mean ( and scaling means dividing with its standard deviation. 
Mathematically, normalization can be expressed as:  
 
Z = (𝑋−x) / 𝜎 
 
In Python, element-wise mean and element-wise standard deviation can be obtained by using .mean() and .std() calls.  
 
In this problem, create a random 5 x 5 ndarray and store it to variable X. Normalize X. Save your normalized ndarray as X_normalized.npy 

    -- CODE --
    
    import numpy as np   //import the numpy library//

    X = np.random.random((5,5))  //generate random values for a 5x5 array//
    
    mean = X.mean()  //calculate the mean of array X//
    std = X.std()    //calculate the standard deviation of array X//
    
    Z = (X - mean) / std   //normalize  array X by inputting the given formula above//

    np.save('X_normalized.npy', X)    //save array X to a file named "X_normalized.npy"//
    
    data = np.load('X_normalized.npy')     //load the saved array file//
    data

---- DIVISIBLE BY 3 PROBLEM ----

 Create the following 10 x 10 ndarray: 
 
               A = 
     [1    4    ⋯   81    100
      ⋮     ⋮    ⋱    ⋮      ⋮
      ⋮     ⋮    ⋱    ⋮      ⋮ 
      ⋮     ⋮    ⋱    ⋮      ⋮
    8281  8464  ⋯  9801  10000]
 
which are the squares of the first 100 positive integers.  
 
From this ndarray, determine all the elements that are divisible by 3. Save the result as div_by_3.npy

    -- CODE -- 

    import numpy as np    //import the numpy library//

    A = np.arange(1,101).reshape(10,10)**2     //create a 10x10 array with the squares of the first 100 positive integers//
    
    Y = A[A % 3 == 0]   //determine if the element is divisible by 3//

    np.save('div_by_3.npy', Y)     //save array Y to a file named "div_by_3.npy"//

    data = np.load('div_by_3.npy')      //load the saved array file//    
    data
    
