# Algorithm for QR Decomposition

## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.

## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

<img width="328" height="122" alt="image" src="https://github.com/user-attachments/assets/f82f8128-2742-4236-9a10-d02cfc4ae2ea" />





<img width="98" height="59" alt="image" src="https://github.com/user-attachments/assets/e08546e6-dda4-427c-a292-de2f5287f0b3" />


<img width="110" height="66" alt="image" src="https://github.com/user-attachments/assets/e31b0a62-3613-496b-aca1-22cbf5cf97ff" />


3.	Obtain the Q matrix   
    <img width="224" height="44" alt="image" src="https://github.com/user-attachments/assets/fc348aa0-49a9-4ed5-aa83-695e4a8d94d5" />

4.	Construct the upper triangular matrix R
   <img width="279" height="87" alt="image" src="https://github.com/user-attachments/assets/b91026e3-c466-4035-9a6d-34103b8e4985" />




## Program:

### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: NITHISH S
RegisterNumber: 212224240105

import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j]*Q[:,j])
        
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,n):
            R[i,j]=A[:,j]@Q[:,i]
            
    print("The Q Matrix is")
    print("" ,Q)
    print("The R Matrix is")
    print("", R)
a = np.array(eval(input()))
QR_Decomposition(a)


```

## Output

<img width="1158" height="603" alt="image" src="https://github.com/user-attachments/assets/7bdaad5c-5074-4ce2-b077-d7a5b085c119" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
