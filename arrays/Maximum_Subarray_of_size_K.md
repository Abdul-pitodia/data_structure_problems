# Maximum sum subarray of size K
## Given an array of integers Arr of size N and a number K. Return the maximum sum of a subarray of size K.

 
```
Example 1:

Input:
N = 4, K = 2
Arr = [100, 200, 300, 400]
Output:
700
Explanation:
Arr3  + Arr4 =700,
which is maximum.
 
```
```
Example 2:

Input:
N = 4, K = 4
Arr = [100, 200, 300, 400]
Output:
1000
Explanation:
Arr1 + Arr2 + Arr3  
+ Arr4 =1000,
which is maximum.

```
## Code

```
def maximumSumSubarray (K,Arr,N):
    # code here 
    i = 0 
    j = 0
    maxx = float('-inf')
    summ = 0

    while j < N:
        summ += Arr[j]

        if (j-i+1) < K:
            j += 1

        elif (j-i+1) == K:
            maxx = max(summ,maxx)
            summ -= Arr[i]
            i += 1
            j += 1


    return maxx
        
```
