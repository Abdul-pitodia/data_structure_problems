Given an unsorted integer array, find the smallest missing positive integer.

Example 1:

Input: [1,2,0]
Output: 3
Example 2:

Input: [3,4,-1,1]
Output: 2
Example 3:

Input: [7,8,9,11,12]
Output: 1
Follow up:

Your algorithm should run in O(n) time and uses constant extra space.


```
class Solution:
    def firstMissingPositive(self, nums: List[int]) -> int:
        a = nums
        n = len(nums)
        
        for i in range(n):
            
            correct_pos = a[i] - 1
            
            while (1 <= a[i] <= n and a[correct_pos] != a[i] ):
                a[i],a[correct_pos] = a[correct_pos],a[i]
                correct_pos = a[i] - 1
        
        print(a)
        for i in range(n):
            if (a[i] != i+1):
                return i+1
        return n+1


```
