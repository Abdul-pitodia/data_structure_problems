# Merge Sort implementation

Time complexity - O(N*LogN)
Space complexity - O(N) or O(LogN)

```
def divide(arr):
    if len(arr)==1:
        return arr
    
    mid_idx = len(arr) // 2
    left = arr[:mid_idx]
    right = arr[mid_idx:]


    left_arr = divide(left)
    right_arr = divide(right)
    
    return merge(left_arr,right_arr)

    

def merge(L,R):
    sortedArray = [None]*(len(L)+len(R))
    k = j = i = 0

    while i<len(L) and j<len(R):
        if L[i] < R[j]:
            sortedArray[k] = L[i]
            i += 1
        else:
            sortedArray[k] = R[j]
            j += 1
        
        k += 1
    
    while i < len(L):
        sortedArray[k] = L[i]
        i += 1
        k += 1

    while j < len(R):
        sortedArray[k] = R[j]
        j += 1
        k += 1
    
    return sortedArray



arr = [12, 11, 13, 5, 6, 7]
#print(arr)

print(divide(arr))

```
