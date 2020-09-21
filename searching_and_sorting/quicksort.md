# Quicksort Algorithm Implementation
Time complexity- O(N*LogN) (average / best)
Space complexity - O(LogN) (with tail call optimisation + smaller subarray processing)



```
def quicksort(arr):
    quickSortHelper(arr, 0, len(arr)-1)
    return arr

def quickSortHelper(arr, startIdx, endIdx):
    if startIdx >= endIdx:
        return
    

    pivot = startIdx
    leftIdx = startIdx + 1
    rightIdx = endIdx

    while rightIdx >= leftIdx:
        if arr[leftIdx] > arr[pivot] and arr[rightIdx] < arr[pivot]:
            swap(leftIdx,rightIdx,arr)

        if arr[leftIdx] < arr[pivot]:
            leftIdx += 1
        
        if arr[rightIdx] > arr[pivot]:
            rightIdx += -1

    swap(pivot, rightIdx, arr)

    leftSubArrayIsSmaller = (rightIdx - 1 - startIdx) < (endIdx-leftIdx)

    if leftSubArrayIsSmaller:
        quickSortHelper(arr,startIdx,rightIdx-1)
        quickSortHelper(arr,leftIdx,endIdx)
    else:
        quickSortHelper(arr,leftIdx,endIdx)
        quickSortHelper(arr,startIdx,rightIdx-1)
        
        

def swap(i, j, arr):
    #print(i,j)
    arr[i],arr[j] = arr[j],arr[i]


arr = [4,5,1,7,3,2,9,8]
print(arr)

print(quicksort(arr))
    
```    


