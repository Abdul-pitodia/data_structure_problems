733. Flood Fill


An image is represented by a 2-D array of integers, each integer representing the pixel value of the image (from 0 to 65535).

Given a coordinate (sr, sc) representing the starting pixel (row and column) of the flood fill, and a pixel value newColor, "flood fill" the image.

To perform a "flood fill", consider the starting pixel, plus any pixels connected 4-directionally to the starting pixel of the same color as the starting pixel, plus any pixels connected 4-directionally to those pixels (also with the same color as the starting pixel), and so on. Replace the color of all of the aforementioned pixels with the newColor.

At the end, return the modified image.

Example 1:
Input: 

image = [[1,1,1],[1,1,0],[1,0,1]]
sr = 1, sc = 1, newColor = 2

Output: [[2,2,2],[2,2,0],[2,0,1]]

Explanation: 
From the center of the image (with position (sr, sc) = (1, 1)), all pixels connected 
by a path of the same color as the starting pixel are colored with the new color.
Note the bottom corner is not colored 2, because it is not 4-directionally connected
to the starting pixel.

Note:
The length of image and image[0] will be in the range [1, 50].
The given starting pixel will satisfy 0 <= sr < image.length and 0 <= sc < image[0].length.
The value of each color in image[i][j] and newColor will be an integer in [0, 65535].


```
class Solution:
    def floodFill(self, image: List[List[int]], sr: int, sc: int, newColor: int) -> List[List[int]]:
        prev_fill = image[sr][sc] 
        r,c = sr,sc
        number_to_fill = newColor
        ff(image,r,c,number_to_fill,prev_fill)
        return image
    
    
def ff(mat,r,c,num_to_fill,prev_fill):
      if r >= len(mat) or r < 0 or c < 0 or c >= len(mat[0]):
        return

      if mat[r][c] != prev_fill:
        return

      if mat[r][c] == num_to_fill:
        return

      mat[r][c] = num_to_fill

      ff(mat,r-1,c,num_to_fill,prev_fill)
      ff(mat,r+1,c,num_to_fill,prev_fill)
      ff(mat,r,c-1,num_to_fill,prev_fill)
      ff(mat,r,c+1,num_to_fill,prev_fill)

        
```

For custom input matrix :

```
def floodfill(mat,r,c,num_to_fill,prev_fill):
  rows,columns = len(mat),len(mat[0])

  if r >= rows or r < 0 or c < 0 or c >= columns:
    return
  
  if mat[r][c] != prev_fill:
    return
  
  mat[r][c] = num_to_fill

  floodfill(mat,r-1,c,num_to_fill,prev_fill)
  floodfill(mat,r+1,c,num_to_fill,prev_fill)
  floodfill(mat,r,c-1,num_to_fill,prev_fill)
  floodfill(mat,r,c+1,num_to_fill,prev_fill)

  #return mat

n = int(input())
mat = [
  [int(k) for k in input().split()] 
  for x in range(n)
]

print(mat)
floodfill(mat,1,2,3,2)
print(mat)


```
