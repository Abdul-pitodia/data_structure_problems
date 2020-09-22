# Print All Sub sequences of a given string
### Approach - Use Recursive Tree method to determine output at each stage 
```
## Substring 
Given input - abc
Output valid sub string - bc
Should be contiguous.

## Subsequence
Given input - abc
Output valid subsequence - ab,bc,abc,a,b,c,ac
Need not be contiguous but should be in order wrt to input

## Subset
All possible permutations
```

Code -
## Subsequence
```
def solve(ip,op,op_lst):
  
  if len(ip) == 0:
    op_lst.append(op)
    return 
    
  
  op1 = op
  op2 = op

  op2 += ip[0]
  solve(ip[1:],op1,op_lst)
  solve(ip[1:],op2,op_lst)

  return 


inp = 'aab'
op = ''
lst = []
solve(inp,op,lst)
print(lst)

```

## Unique Subsequence - Use a set, or compare if subsequence already exists.
Code:
```
def solve(ip,op,op_lst):
  
  if len(ip) == 0:
    #print(op)
    if op in op_lst:
      return
    else:
      op_lst.append(op)
    return 
    
  
  op1 = op
  op2 = op

  op2 += ip[0]
  solve(ip[1:],op1,op_lst)
  solve(ip[1:],op2,op_lst)

  return 


inp = 'aab'
op = ''
lst = []
solve(inp,op,lst)
print(lst)

```
