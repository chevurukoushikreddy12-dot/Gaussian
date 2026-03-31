# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm:
## 1.Start the program and import the required Python libraries NumPy and sys. Read the number of variables and the augmented matrix as input
## 2.Apply Gaussian elimination to convert the augmented matrix into an upper triangular matrix using row operations. 3.Perform back substitution to calculate the values of the unknown variables.
## 3.Display the solution of the variables and stop the program.


## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: chevuru koushik
RegisterNumber: 212225240028
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detect!')
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio*a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2, -1, -1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i]-a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f '%(i,x[i]),end='')


```

## Output:
<img width="1192" height="873" alt="maths for ai exp-6" src="https://github.com/user-attachments/assets/65f6f7e2-ee14-4118-b7ed-0f2740b672a6" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

