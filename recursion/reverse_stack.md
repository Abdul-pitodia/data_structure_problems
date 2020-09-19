
# reverse a stack
```
def reverse(arr):
  if len(arr) == 1:
    return
  
  temp = arr.pop()
  reverse(arr)
  insert(arr,temp)
  return arr

def insert(arr,temp):
  if len(arr) == 0:
    arr.append(temp)
    return
  
  val = arr.pop()
  insert(arr,temp)
  arr.append(val)
  #return arr

arr = [10,9,1,7,4]
print(reverse(arr))
```
