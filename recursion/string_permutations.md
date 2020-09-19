
# String permutations

```
def permut(lst,temp_lst):
  if len(lst) == 1:
    return lst

  temp = lst.pop()
  permut(lst,temp_lst)

  i = 0
  for word in lst:
    word = list(word)
    #print(word)
    ln = len(word)
    while i < (ln + 1):
      wd = ''
      word.insert(i,temp)
      wd = ''.join(word)
      temp_lst.append(wd)
      #del word[i]
      word.pop(i)
      i += 1
    i = 0    //DID NOT RESET I AND WORD.
    word.clear()
  
  // clear og list to fill new permutation result
  lst.clear()
  for i in range(len(temp_lst)):
    lst.insert(i,temp_lst[i])

  #print(lst)
  temp_lst.clear() // if dont clear this , then previous results will be there
  return lst
  
  

string_to_permute = input()
string_to_permute = list(string_to_permute)
print()
for permu in permut(string_to_permute,[]):
  print(permu)

#print('ans',permut(string_to_permute,[]))

```
