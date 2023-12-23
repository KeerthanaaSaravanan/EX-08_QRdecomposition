# EX-08: Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
  ![Screenshot 2023-12-23 152643](https://github.com/KeerthanaaSaravanan/EX-08_QRdecomposition/assets/145742596/104ef04b-965d-427f-8584-69e4ec2f3968)

4.	Obtain the Q matrix   
   ![Screenshot 2023-12-23 152648](https://github.com/KeerthanaaSaravanan/EX-08_QRdecomposition/assets/145742596/5babcbeb-b182-4fa2-b0a7-40b2befc1411)


5.	Construct the upper triangular matrix R
   ![Screenshot 2023-12-23 152653](https://github.com/KeerthanaaSaravanan/EX-08_QRdecomposition/assets/145742596/e4e0aa6c-2f4f-403c-a0b3-b07de526ba60)

## Program:
### Gram-Schmidt Method
```
'''
Program to QR decomposition using the Gram-Schmidt method
Developed by: KEERTHANA S
RegisterNumber: 23013398
'''
import numpy as np
def QR_Decomposition(A):
    n,m = A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0] = A[:,0]
    Q[:,0] = u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(a[:,i]@Q[:,j])*Q[:,j]
        Q[:,i] = u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=a[:,j]@Q[:,i]
    print(Q)        
    print(R)
    
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output
![Screenshot 2023-12-23 151613](https://github.com/KeerthanaaSaravanan/EX-08_QRdecomposition/assets/145742596/619d6e93-06d0-4a1c-8989-adf0e15e16fe)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
