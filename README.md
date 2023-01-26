# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Importing numpy and getting the input for number of unknowns
2. Creating zero matrices a and x for solution using np.zeros() 
3. Getting the input for the elements of the matrix using a nested for loop
4. Finding the ratio and using the ratio to get the matrix into row reduction form
5. Reverse substituting the value to the x matrix using a for loop
6. Printing the values of the unknown variable
## Program:
```py
#Program to find the solution of a matrix using Gaussian Elimination.
#Developed by: Sanjay Ragavendar M K
#RegisterNumber: 22009286

import numpy as np
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
        
for i in range(n):
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
            
x[n-1] =a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
        
    x[i] = x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end=' ')
```

## Output:
![image](https://user-images.githubusercontent.com/91368803/214783265-1fca871b-28c6-459f-ba38-cc4e9bab0675.png)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

