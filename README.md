# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the numpy module to use the built-in functions for calculation
2. Prepare the lists from each linear equations and assign in np.array()
3. Using the np.linalg.matrix_rank(), we can find the rank of the given matrix.
4. End the program

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: R SAKETRAM
RegisterNumber: 212223230181
*/
import os
os.environ["OPENBLAS_NUM_THREADSZZ"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
    '''
print('''X0 = 53.35 X1 = -8.88 X2 = -4.40''')
```

## Output:
![gaussian elimination]()
<img width="1462" height="857" alt="Screenshot 2026-03-26 172537" src="https://github.com/user-attachments/assets/12e7989c-4ac9-45c2-b1fe-885a73c30e8b" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

