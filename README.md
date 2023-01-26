# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
![1](https://user-images.githubusercontent.com/120552008/214865181-184793d0-49f4-44c7-af9e-3ccf523af8ea.png)
![2](https://user-images.githubusercontent.com/120552008/214865236-0fa4f537-2cf4-4fde-8616-3b07fa9f5b2b.png)

![3](https://user-images.githubusercontent.com/120552008/214865301-f9e4615f-d76b-440f-ae92-bf107c802f8f.png)


3.	Obtain the Q matrix   
   ![4](https://user-images.githubusercontent.com/120552008/214865387-8c206bf2-13ff-4610-bbf4-4a076e9d82d3.png)

4.	Construct the upper triangular matrix R
   ![5](https://user-images.githubusercontent.com/120552008/214865440-96da9b58-f5cd-44f2-a982-3503ca18c108.png)



## Program:
### Gram-Schmidt Method
```python
Developed by:Dinesh Karthick.K.J
RegisterNumber: 22005847

import numpy as np
arr =np.array(eval(input()))
n,m=arr.shape
u=np.empty((n,m))
e=np.empty((n,m))
u[:,0]=arr[:,0]
e[:,0]=u[:,0]/np.linalg.norm(u[:,0])
for i in range(1,n):
    u[:,i]=arr[:,i]
    for j in range(i):
        u[:,i]-=(arr[:,i]@e[:,j])*e[:,j]
        e[:,i]=u[:,i]/np.linalg.norm(u[:,i])
R=np.zeros((n,m))
for i in range(n):
    for j in range(i,m):
        R[i,j]=arr[:,j]@e[:,i]
print(e)
print(R)


```

## Output
![6](https://user-images.githubusercontent.com/120552008/214865486-2495bdd4-c7eb-4ee8-8655-1ede7567da84.png)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
