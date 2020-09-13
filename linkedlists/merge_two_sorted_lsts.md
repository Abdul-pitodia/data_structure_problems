21. Merge Two Sorted Lists
Easy


Merge two sorted linked lists and return it as a new sorted list. The new list should be made by splicing together the nodes of the first two lists.

Example:

Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4



```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        new_lst = ListNode(0)
        head = new_lst
        
        while l1 and l2:
            if l1.val < l2.val:
                new_lst.next = l1
                l1 = l1.next
            
            else:
                new_lst.next = l2
                l2 = l2.next
            
            new_lst = new_lst.next
            
        if l1:
            new_lst.next = l1
        else:
            new_lst.next = l2
                


        return head.next

```
        

    
        
        
