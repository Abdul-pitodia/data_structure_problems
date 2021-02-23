If the current element adds value to the previous sum, (meaning the addition of current element to the currentsum is greater than the element itself), then join along the subarray.
Else, start your own sub array.

```
def maxSubArraySum(a,size):
    current_best = a[0]
    overall_best = a[0]
    
    for i in range(1, size):
        if (a[i] < current_best + a[i]):
            current_best = current_best + a[i]
        else:
            current_best = a[i]
            
        
        overall_best = max(overall_best, current_best)
    
    return overall_best
```

https://practice.geeksforgeeks.org/problems/kadanes-algorithm-1587115620/1
