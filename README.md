# 2ECE - A: PA-2 - Number Python (NumPy) Test

<i>About the files:</i><br>
<u>X_normalized.npy</u> - A NumPy array file that loads the <i>Normalization Problem</i><br>
<u>div_by_3.npy</u> - A NumPy array file that loads the <i>Divisible by 3 Problem</i><br>
<u>PA2 - Number Python</u> - Python file where the array files would be loaded.
<br>
<br>
<b>X_normalized.npy (Normalization Problem)</b><br>
A Python script that 'normalizes' a given array. It creates a random 5 x 5 array where it then is labeled as 'X' (the elements in the array changes everytime it is ran). Furthermore, it calculates the standard deviation and mean of the elements in array 'X'. Lastly, the elements in Array 'X' is then subracted by its mean element-wise where their difference is then divided by the calculated standard deviation of all the elements in array 'X'.

The array that would be the quotient would be saved as <u>'X_normalized.npy'</u>

```python
import numpy as np #Imports the NumPy Library.

X = np.random.random((5,5)) #Creates a 5 x 5 array where its values are random.

SD = X.std() #Gets the standard deviation of the elements in array 'X'
MEAN = X.mean() #Gets the mean of the elements in array 'X'.

Y = X - MEAN #The variable 'Y' gets the difference of the array 'X' and the mean.
X_normalized = Y/SD #The variable 'Z' gets the quotient of the variable 'Y' and the standard deviation.

np.save('X.normalized.npy', X_normalized) #Saves the output as a NumPy array for loading.
```

<b>div_by_3.npy (Divisible by 3 Problem)</b><br>
A Python script where it creates a 10 x 10 array on which the elements are all the squared values of the first positive 100 integers. With this array, it then creates a different array where it finds the elements that are divisible by 3. 

The newly created array where it displays all the elements divisible by 3 would be saved as <u>'div_by_3.npy'</u>

```python
import numpy as np #Imports the NumPy Library.

a = np.arange(1,101) #Creates an array that displays the first 100 integers.
a.resize(10,10) #Resizes array to a 10 x 10 size.
b = a**2 #Squares the array element-wise.

div_by_3 = b[b%3 == 0] #Checks the array 'B' element-wise if the element is divisible by 3 using a modulus operator.

np.save("div_by_3.npy", div_by_3) #Saves the output as a NumPy array for loading.
```

<b>PA2 - Number Python</b><br>
A Python script where it loads the NumPy array files mentioned and saved above. 

```python
import numpy as np #Imports the NumPy Library.

data = np.load("X_normalized.npy", allow_pickle=True)
data
    #Loads the .npy for the Normalization Problem.

data2 = np.load('div_by_3.npy', allow_pickle=True)
data2 
    #Loads the .npy for the Divisible by 3 Problem.
```
