# Binary Search algorithm
Time complexity - O(LogN)
Space Complexity - O(1)

```
# [11,16,32,44,67,78,91]
# search 32 in this

def binary_search(arr,target):
    left = 0
    right = len(arr) - 1

    while left <= right:
        mid = (left + right) // 2

        if arr[mid] > target:
            right = mid - 1
        
        elif arr[mid] == target:
            print(f'Number {target} found at position {mid}')
            return

        else:
            left = mid + 1
    
    print('Number not found in the array')
        



arr = [11,16,32,44,67,78,91]
binary_search(arr,67)

```
