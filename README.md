# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

Read the number of unknowns.
Form the augmented matrix using the coefficients and constants.
Apply Gaussian Elimination to convert the matrix into upper triangular form.
Use back substitution to find the values of the unknowns.
Display the solution.

## Program:
```
/*
2
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: S R NIVEDHITHA
RegisterNumber: 212225240102
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k  in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f" % (i, x[i]),end=" ") 
*/
```

## Output:
![gaussian elimination]()
<img width="439" height="812" alt="Screenshot 2026-05-20 132532" src="https://github.com/user-attachments/assets/8e05544f-d6e8-4758-a81f-b4cbd1f2ffe5" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

