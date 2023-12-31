# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![8 maths](https://github.com/MOHAMEDAAKIFASRAR/QRdecomposition/assets/148514683/4e82fb84-0417-4e09-a693-6355fa6a0ebe)


    

    

3.	Obtain the Q matrix Q=(e1|e2|... ... ...en) 
    
4.	Construct the upper triangular matrix R
    ![exp 8](https://github.com/MOHAMEDAAKIFASRAR/QRdecomposition/assets/148514683/29a30d8f-f3f1-428d-b067-33756bd758b6)




## Program:

### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: MOHAMED AALKIF ASRAR S
RegisterNumber: 23003613
'''
import numpy as np
def QR_Decomposition(A):
    n, m = A.shape # get the shape of A
    
    Q = np.empty((n,n)) # initialize matrix Q
    u = np.empty((n,n)) # initialize matrix u
    
    u[:, 0] = A[:, 0]
    Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])
    
    for i in range(1, n):
        
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j] # get each u vector
            
            Q[:, i] = u[:, i] / np.linalg.norm(u[:, i]) # compute each e vector
            
    R = np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output
![Screenshot 2023-12-28 191838](https://github.com/MOHAMEDAAKIFASRAR/QRdecomposition/assets/148514683/76b78517-5af9-4288-ac53-34200ff40078)


```

## Result

The QR decomposition algorithm using  Gram-Schmidt process is written and verified the result
