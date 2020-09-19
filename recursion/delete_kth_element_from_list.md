
delete middle/ kth element of list
 
[1,2,3] - [1,3] # pop 3, save it somewhere 
 
[1,2] - [1]  # i got 1, i need to append 3 here

hypo - solve(list,k) - deleted kth element

base cond - if k == 1, we got the element 
```
def solve(lst,k):
  if k == 1:
    lst.pop()
    return lst
  
  target = lst.pop()
  solve(lst,k-1)
  lst.append(target)
  return lst

arr = [1,2,3,4,5,6,7]
print(solve(arr,1))
```

the k is measured from end of list, as it is emulating a stack
