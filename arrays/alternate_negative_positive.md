Arrange the array in place and in O(n) and O(1) space such that the elements are in alternating fashion of negatives and positives

For example, consider - [-5, -2, 5, 2, 4, 7, 1, 8, 0, -8]
The output for this can be ordered or unordered
Ordered meaning, the order of elements is same , i.e. negative elements follow the order in which they were initially , same for positive
Un ordered meaning the order in which elements appear in output doesnt matter

So, ordered output is - [-5, 5, -2, 2, -8, 4, 7, 1, 8, 0]
Un ordered is - [-5, 5, -2, 2, -8, 7, 1, 8, 0, 4]
(In unordered, negatives are -> -5, -2, -8 (in order) , but positives are -> 5,2,7,1,8,0,4 as opposed to 5,2,4,7,1,8,0 which is ordered)

There are two approaches thus, for ordered and un-ordered, both in o(n) and o(1)

Unordered Approach -
This basically checks if the number at current index is negative or positive, depending upon whether index is odd or even.
If a match is found, then a correct element for that particular index is found using while loop which breaks when right element is found
Then a swap takes place, and thus the order is not maintained

```
for i in range(len(inp)):
    j = i + 1
    if (i%2 == 0 and inp[i] < 0) or (i%2 != 0 and inp[i] > 0):
        continue

    elif (i%2 != 0 and inp[i] < 0):
        while (j < len(inp)):
            if inp[j] > 0:
                break
            j = j + 1
        if j == len(inp):
            continue
        else:
            inp[i], inp[j] = inp[j], inp[i]


    elif (i%2 == 0 and inp[i] > 0):
        while (j < len(inp)):
            if inp[j] < 0:
                break
            j = j + 1
        if j == len(inp):
            continue 
        else:
            inp[i], inp[j] = inp[j], inp[i]


    else:
        pass
        
```

Ordered Approach -
In this approach, the element which is outof place, is found and its index is noted. Then a matching element is found and its index is also noted
These two indicies are now used to make a subarray and right rotate it
Thus, all elements are shifted and thus order is maintained

```
not_proper = -1
current = 0
for i in range(len(inp)):

    if ((i%2 != 0 and inp[i] < 0) or (i%2 == 0 and inp[i] > 0)) and (not_proper == -1):
        not_proper = i 
        continue
    
    if ((inp[not_proper] < 0 and inp[i] > 0) or (inp[not_proper] > 0 and inp[i] < 0)) and (not_proper > 0):
        temp = inp[i]
        for i in range(i, not_proper, -1):
            inp[i] = inp[i-1]
        inp[not_proper] = temp 
        not_proper = -1 
        
```

