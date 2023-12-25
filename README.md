# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

   ![ex4](https://github.com/ILAIYADEEPAN/QRdecomposition/assets/147473334/e061b41a-c16b-4656-a8df-62abf98c76b5)


    ![ex6](https://github.com/ILAIYADEEPAN/QRdecomposition/assets/147473334/56694c92-e114-4f0d-85bb-fe325c7eb51d)


   ![ex3](https://github.com/ILAIYADEEPAN/QRdecomposition/assets/147473334/d281b791-ffb0-4541-9489-3d4c48bcc540)


3.	Obtain the Q matrix   
   ![ex1](https://github.com/ILAIYADEEPAN/QRdecomposition/assets/147473334/91fe3a08-0c92-4d3e-8ee8-8747b3ae3cfb)

4.	Construct the upper triangular matrix R
   ![ex2](https://github.com/ILAIYADEEPAN/QRdecomposition/assets/147473334/8d55dbc0-aed5-439e-9a81-de341da5514e)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: ILAIYADEEPAN . k
RegisterNumber: 23013535
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range (1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i] -=(A[:,i] @ Q[:,j] * Q[:,j])
        Q[:,i]=u[:,i] / np.linalg.norm (u[:,i])
    R = np.zeros((n,m))
    for i in range (n):
        for j in range(i,m):
            R[i,j]=A[:,j] @ Q[:,i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output
![Algorithm output](https://github.com/ILAIYADEEPAN/QRdecomposition/assets/147473334/a12ec745-43b5-43f3-a3a3-fe0e0e71a0a8)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
