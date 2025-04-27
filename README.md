# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Convert the system of equations into an augmented matrix.Swap rows if necessary to ensure that the pivot element is non-zero. 
2. After converting the matrix into an upper triangular form, solve the system of equations by substituting the values of the variables starting from the last row.
3. Start from the last row and substitute the known values into the equations above to find the values of the variables.
4. This program will solve the system of equations A×X=B, where A is the coefficient matrix and B is the constant matrix.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: YAZHINI R R
RegisterNumber: 212224100063
*/
```
```
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
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
            
            
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]

for i in range(n):
    print('X%d = %0.2f'%(i,x[i]), end=' ')
```

## Output:
![Screenshot 2025-04-27 162450](https://github.com/user-attachments/assets/de7e259b-7647-4867-b394-c55e60efca59)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

