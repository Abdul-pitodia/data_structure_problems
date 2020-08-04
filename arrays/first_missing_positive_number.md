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
        
        # iterate from 0 to n
        
        for i in range(n):
            
            correct_pos = a[i] - 1  #calculate the correct position for current element
            
            while (1 <= a[i] <= n and a[correct_pos] != a[i] ):  # check if current element lies in range , and if yes also check if it is not placed at the correct position
                a[i],a[correct_pos] = a[correct_pos],a[i]        # if it is not present at its correct position, swap the number with the number present at the correct position
                correct_pos = a[i] - 1                           # it may happen that new swapped number will lie in range and not in correct position. hence we use a while loop
                                                                 # so we calculate correct pos for new element again and do swapping again.
        
        for i in range(n):
            if (a[i] != i+1):
                return i+1
        return n+1


```



https://www.geeksforgeeks.org/find-the-smallest-positive-number-missing-from-an-unsorted-array-set-3/?ref=rp
https://www.youtube.com/watch?v=-lfHWWMmXXM
