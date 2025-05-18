# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
Step 1: Start the Program.
Step 2: Import required libraries:
numpy for array handling.
sys to exit the program in case of divide-by-zero.

Step 3: Input the Size and Augmented Matrix
Read the number of unknowns n.

Create an augmented matrix a of size n × (n+1) and a solution vector X of size n.
Take user input to fill the augmented matrix a.

Step 4: Forward Elimination
For each pivot row i, check for divide-by-zero.

For all rows below i, compute the ratio a[j][i]/a[i][i] and eliminate the coefficient below the pivot.

Step 5: Solve the last variable directly.
Step 6: Solve remaining variables using previously computed values.
Step 7: Print the values of all unknowns.
```
## Program:
```
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: LUKESH M
RegisterNumber: 212224230144
```
```
import numpy as np
import sys

# Reading number of unknowns
n = int(input())

a = np.zeros((n,n+1))

# Making numpy array of n x n+1 size and initializing
# To zero for string solution vector
x = np.zeros(n)

# Reading augmented matrix coefficients
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
        
# Applying Gauss Elimination

for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
            
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
# Back Substitution

x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i]-a[i][j]*x[j]
        
    x[i] = x[i]/a[i][i]
    
# Displaying solution
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![ex 06](https://github.com/user-attachments/assets/e38a5f0e-f48f-413e-b0dc-93af35b2bb0f)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

