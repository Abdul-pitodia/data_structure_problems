Use two pointer approach, increment left when negative number encountered
Increment right when positive number encountered
Why? because left pointer denotes that a negative number is towards left
and right pointer indicates that positive number is towards right
So, when these two are opposite, i.e. left pointer has a positive element, and right pointer has a negative element, swap them
Else, increment them both (as there is no point to swap)
Do untill j becomes less than i ( right pointer passes the left one )


```
arr = [-12, -11, -13, -5, -6, 5, -7, -3, -6]

i = 0
j = len(arr) - 1

while j >= i:
	# print(i,j)

	if arr[i] < 0 :
		i += 1

	elif arr[j] > 0:
		j -= 1
	
	elif (arr[i] > 0 and arr[j] < 0):
		# print(arr[i], arr[j])
		arr[i], arr[j] = arr[j], arr[i]

	else:
		i += 1
		j -= 1


print(arr)
```
