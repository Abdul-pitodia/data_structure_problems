104. Maximum Depth of Binary Tree
Easy

Given a binary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

Note: A leaf is a node with no children.

Example:

Given binary tree [3,9,20,null,null,15,7],

    3
   / \
  9  20
    /  \
   15   7
return its depth = 3.



```
Definition for a binary tree node.
class TreeNode:
     def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right
class Solution:
    def maxDepth(self, root: TreeNode) -> int:
        current,cnt = root,0
        lst = []
        if not root:
            return 0
        
        def depth(root,cnt):
            if root is None:
                lst.append(cnt)
                return
        
            depth(root.left,cnt+1)
            depth(root.right,cnt+1)
        
        depth(root,cnt)
    
        return max(lst)

```    


        

        
        
        
