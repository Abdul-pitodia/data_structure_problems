Given an array A of size N, construct a Product Array P (of same size) such that P is equal to the product of all the elements of A except A[i].

Input:
The first line of input contains an integer T denoting the number of test cases. T testcases follow. Each testcase contains two lines of input. The first line is N. The second line contains N elements separated by spaces.

Output:
For each testcase, print the Product array P.

Constraints:
1 <= T <= 10
1 <= N <= 1000
1 <= Ai <= 20

Example:
Input:
2
5
10 3 5 6 2
2
12 20
Output:
180 600 360 300 900
20 12

Explanation:
Testcase1: For the product array P, at i=0 we have 3*5*6*2. At i=1 10*5*6*2. At i=2 we have 10*3*6*2. At i=3 we have 10*3*5*2. At i=4 we have 10*3*5*6
So P is 180 600 360 300 900


O(N) SOLUTION:

```
#code
test = int(input())

def prod(size,arr):
    left_prod = [1]*size
    right_prod = [1]*size
    new_prod = [1]*size
    temp = 1
    
    for i in range(size):
        left_prod[i] = temp
        temp = temp * arr[i]
    
    temp = 1
    for i in range(size-1,-1,-1):
        right_prod[i] = temp
        temp = arr[i]*temp
        
    for i in range(size):
        new_prod[i] = left_prod[i]*right_prod[i]
        
    for i in range(size):
        print(new_prod[i],end=' ')

for i in range(test):
    arr_size = int(input())
    arr = [int(i) for i in input().strip().split()]
    prod(arr_size,arr)



'''
