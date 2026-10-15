# Merge-Nodes-in-Between-
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeNodes(self, head: ListNode | None) -> ListNode | None:
        if head is None:
            return None
        r=[]
        while head:
            r.append(head.val)
            head=head.next
        n=len(r)
        r1=[]
        c=0
        for i in range(1,n):
            if r[i]==0:
                if c!=0:
                   r1.append(c)
                c=0
            else:
                c+=r[i]
        d=ListNode(0)
        temp=d
        for i in r1:
            temp.next=ListNode(i)
            temp=temp.next
        return d.next
