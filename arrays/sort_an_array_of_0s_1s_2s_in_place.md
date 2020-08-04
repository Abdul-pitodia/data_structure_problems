Sort an array of 0s 1s and 2s in place without any sorting algorithm in O(n) time

Given an array of size N containing 0s, 1s, and 2s; sort the array in ascending order.

Input:
First line of input contains number of testcases T. For each testcase, there will be two lines, first of which will contain N. The second lines contains the elements of the array.

Output: 
Print sorted array.

Your Task:
Complete the function sort012() that takes array and n and sorts the array in place. 

Constraints: 
1 <= T <= 50
1 <= N <= 10^5
0 <= A[i] <= 2

Example:
Input :
2
5
0 2 1 2 0
3
0 1 0

Output:
0 0 1 2 2
0 0 1

Explanation:
Testcase 1: After segragating the 0s, 1s and 2s, we have 0 0 1 2 2 which shown in the output.



```

def sort012(arr,n):
    # code here
    zeros = 0
    ones = 0
    twos = 0
    
    for i in range(n):
        if (arr[i] == 0):
            zeros += 1
        elif (arr[i] == 1):
            ones += 1
        else:
            twos += 1
    
    i = 0
    while (zeros > 0):
        arr[i] = 0
        zeros -= 1
        i += 1
    
    while (ones > 0):
        arr[i] = 1
        ones -= 1
        i += 1
    
    while (twos > 0):
        arr[i] = 2
        twos -= 1
        i += 1
    
    return arr


```



To sort using new array:

```

def sort012(arr,n):
    # code here
    zeros = 0
    ones = 0
    twos = 0
    
    for i in range(n):
        if (arr[i] == 0):
            zeros += 1
        elif (arr[i] == 1):
            ones += 1
        else:
            twos += 1
    
    zero_lst = [0] * zeros
    ones_lst = [1] * ones
    twos_lst = [2] * twos
    arr1 = zero_lst + ones_lst + twos_lst
    print(arr1)
    
    return (arr)
    
    
    
```    
