https://leetcode.com/problems/valid-parentheses/

1. Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

2. An input string is valid if:
Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
 
 
3. Example 1:

Input: s = "()"
Output: true

4. Example 2:

Input: s = "()[]{}"
Output: true

5. Example 3:

Input: s = "(]"
Output: false

6. Example 4:

Input: s = "([)]"
Output: false
7. Example 5:

Input: s = "{[]}"
Output: true


Code
----

```
    def isValid(self, s: str) -> bool:
        
        if (len(s)%2 != 0):
            return False
            
        opens = set(['(', '[', '{' ])
        closes = set([')', ']', '}'])
        compares = set(['()', '[]', '{}'])
        stack = []
        
        for char in s:
            if char in opens:
                stack.append(char)
            
            elif len(stack) == 0:
                return False
            
            elif (char in closes):
                if ((stack[-1] + char) in compares):
                    stack.pop()
                else:
                    return False
                
            else:
                pass
        
        return len(stack) == 0

```
