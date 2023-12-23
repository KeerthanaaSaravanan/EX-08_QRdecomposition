# EX-08: Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
3.	<br>
   ![ex4](https://github.com/KeerthanaaSaravanan/EX-08_QRdecomposition/assets/145742596/2142ce61-6562-4af8-80ee-c8506ac80d44)
   <br>
    ![ex6](https://github.com/KeerthanaaSaravanan/EX-08_QRdecomposition/assets/145742596/2944249c-8796-42f9-bb7c-f0cf33a60045)
    <br>
    ![ex3](https://github.com/KeerthanaaSaravanan/EX-08_QRdecomposition/assets/145742596/07b812d6-968a-4ad4-ae26-0dbaf8c6c108)

4.	Obtain the Q matrix   
    ![ex1](https://github.com/KeerthanaaSaravanan/EX-08_QRdecomposition/assets/145742596/56c3718f-d0e9-480b-bc5a-1f12005edd0e)

5.	Construct the upper triangular matrix R
<br>
    ![ex2](https://github.com/KeerthanaaSaravanan/EX-08_QRdecomposition/assets/145742596/fe7b3002-cb5a-48e4-93f3-52850aaa8285)


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
