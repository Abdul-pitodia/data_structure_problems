#recursion sort

# [3,2,1] -- [1,2,3]
# [3,2] -- [2,3] - insert 1
# [3] - 1 
# [3] - 1
# [] - 1
# [1]
# insert 1 if arr empty, else if 1 > last element

#################################################
```
def sorter(arr):
  if len(arr) == 1:
    return arr

  target = arr.pop()
  #print(arr,target)
  sorter(arr)
  #print(arr,target)
  insert(arr,target)


def insert(arr,target):
  #print(len(arr))
  if len(arr) == 0 or arr[-1] <= target:
    print(arr)
    return arr.append(target)
    

  new_target = arr.pop()
  #print(arr,target)
  insert(arr,target)
  arr.append(new_target)
  

arr = [3,2,1]
sorter(arr)
print(arr)

```
