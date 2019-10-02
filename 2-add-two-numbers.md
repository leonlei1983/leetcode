# 2. Add Two Numbers

You are given two **non-empty** linked lists representing two non-negative integers. The digits are stored in **reverse order** and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

**Example:**

```
Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
Explanation: 342 + 465 = 807.
```

---

```
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        esum = 0
        head = ListNode(0)
        tail = head
        while l1 or l2:
            esum /= 10
            if l1:
                esum += l1.val
                l1 = l1.next
            if l2:
                esum += l2.val
                l2 = l2.next
            tail.next = ListNode(esum % 10)
            tail = tail.next

        esum /= 10
        if esum > 0:
            tail.next = ListNode(esum % 10)
            tail = tail.next
        
        return head.next
```
