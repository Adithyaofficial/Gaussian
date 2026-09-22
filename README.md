# Gaussian Elimination

3.Perform Gaussian elimination to reduce the matrix to upper 
triangular form, ensuring no division by zero.

4.Back substitute to compute solution values for the variables.

5.Print the solution vector formatted to two decimal places.

## Program:
```
'''
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: ADITYAH M S
RegisterNumber: 212223220002
'''
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
    print('X%d = %0.2f' %(i,x[i]),end=' ')

```

## Output:
![Output1](CODE_page-0001.jpg)
![Output2](CODE_page-0002.jpg)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.
