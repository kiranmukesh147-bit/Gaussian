# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1: Import the required libraries and read the order of the matrix and the augmented matrix from the user.

Step 2: Convert the given matrix into upper triangular form by eliminating the elements below the main diagonal using Gaussian elimination.

Step 3: Perform back substitution starting from the last equation to calculate the values of the unknown variables.

Step 4: Display the calculated values of the unknown variables as the solution of the given system of linear equations. 

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Kiran Mukesh K
RegisterNumber: 212225040188
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n= int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit("Divide by zero detected!")
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
    print("X%d = %0.2f " %(i,x[i]), end = "")
```
<img width="1228" height="840" alt="image" src="https://github.com/user-attachments/assets/82b3f609-3df3-4e60-8f91-28f4df32c928" />

## Output:
<img width="1131" height="492" alt="image" src="https://github.com/user-attachments/assets/52296c1c-a20b-4346-b774-84fa27085aca" />




## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

