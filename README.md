# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
1.Start the program.
2.Input the number of equations.
3.Input the augmented matrix (coefficients and constants).
4.Initialize an array to store the solutions.
5.Loop through each row to begin the elimination process.
6.Check for zero pivot; if found, display an error and stop.
7.Eliminate values below the pivot to create an upper triangular matrix.
8.Convert the last row into the last variable's value.
9.Back-substitute: Use the known variables to find the remaining ones, moving upward.
10.Display the solution values for all variables.
```

## Program
```python
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]= a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end = ' ')
```

## Output:

![image](https://github.com/user-attachments/assets/ee45cc41-08ff-4ef8-96fc-26c50319658c)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

