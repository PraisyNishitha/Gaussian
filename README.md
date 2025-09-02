# Gaussian Elimination
## NAME : PRAISY NISHITHA J
## REFERENCE NUMBER: 212224100042
## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

Step 1: Read input and form the augmented matrix of coefficients and constants.
Step 2: Perform forward elimination to reduce the matrix into upper triangular form.
Step 3: Apply back substitution to compute unknowns from last variable to first.
Step 4: Print solution values of all variables.
## Program:
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
        sys.exit('divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f '%(i,x[i]),end='')
```

## Output:
<img width="772" height="979" alt="image" src="https://github.com/user-attachments/assets/4009197b-042e-433a-b7c7-ca690e03b6dc" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

