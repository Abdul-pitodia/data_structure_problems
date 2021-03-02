Next permutation problem 
Determine the next permutation of the given number sequence in lexicographical order.

For example, consider array [1, 3, 5, 4, 2] 
Its next permutation will be [1, 4, 5, 3, 2]

The steps to arrive at this solution are as follows :

```
Firstly lets consider permutations of a simple example, 123

123
132
213
231
312
321
```

*What we do is, we keep the first digit intact (assuming it to be its own place), and then the rest digits are interchanged
*Lexicographic means every digit will be in its ascending order
so we have 3 digits 1 , 2 and 3
so first permutation will start from 1
even in that permutation first permutation starts from 2
then, once 12 is done, we only have another choice 3
So we do 132
*Now, permutations from 1 are done

*We move to 2 and do the same steps

*So, because of this we can see a pattern that when the number from behind is greater than its next immediate neighbour, that is the break point
*before that break point, everything is assumed to be intact at its place, like its sorted in its lexicographic order
*Whatever happens is after that break point, i.e. reshuffling or choosing a start number for next permutation
*So for next permutation, before the break point everything is fixed, the next higher number greater than break point number will be at break points position now
*So we find that next higher number.
*Coming to the example, 1,3,5,4,2
Here break point is 3 ( as 3 < 5)
*Now, for next permutation, we find just highest in 5,4,2 . We get  4 as answer
this will now be in place of 13 . i.e. it will be 14 and next digits will be shuffled.
*These digits will be reversed. 

*Code - 

```
    def nextPermutation(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        
#       [1, 3, 5, 4, 2]
#       [1, 4, 5, 3, 2]
        
        break_point = 0
        i = len(nums) - 1
        
        while i >0 and nums[i] <= nums[i-1]:
            i = i - 1
            
        break_point = i-1
        if break_point < 0:
            return nums.sort()
        
        j = len(nums) - 1
        while nums[j] <= nums[break_point]:
            j -= 1
            
        nums[break_point], nums[j] = nums[j], nums[break_point]
        nums[break_point+1:] = nums[break_point+1:][::-1]

```



