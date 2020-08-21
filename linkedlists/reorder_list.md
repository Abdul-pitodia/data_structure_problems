Given a singly linked list L: L0→L1→…→Ln-1→Ln,

reorder it to: L0→Ln→L1→Ln-1→L2→Ln-2→…

You may not modify the values in the list's nodes, only nodes itself may be changed.

Example 1:

Given 1->2->3->4, reorder it to 1->4->2->3.

Example 2:

Given 1->2->3->4->5, reorder it to 1->5->2->4->3.





```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

# 1 > 2 > 3 > 4 > 5 > 6 > 7

def split_ll(head):
    
    if not head:
        return 
    else:
        curr = head # has head of 1st split list
        slow = head # has head ref of 2nd split list
        fast = head  # tail ref of 2nd split list
        prev = None   # tail of 1st split list

        while fast and fast.next:
            prev = slow
            slow = slow.next
            fast = fast.next.next

        mid = slow.next
        slow.next = None
        return mid

# 1 > 2 > 3 > 4 > null

# 5 > 6 > 7 > null

def reverse_ll(b):
    p1 = None
    p2 = b
    
    while p2:
        p3 = p2.next
        p2.next = p1
        p1 = p2
        p2 = p3
        
    return p1

def merge_ll(a,b):
    while a and b:
        a_next = a.next
        b_next = b.next
        
        a.next = b
        b.next = a_next
        
        a = a_next
        b = b_next
    
    
class Solution:
    def reorderList(self, head: ListNode) -> None:
        """
        Do not return anything, modify head in-place instead.
        """
        l1 = head
        b = split_ll(head)
        l2 = reverse_ll(b)
        merge_ll(l1,l2)
        
        
```        
