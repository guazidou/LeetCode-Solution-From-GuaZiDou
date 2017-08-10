# 问题描述 {#问题描述}

Write a function to delete a node \(except the tail\) in a singly linked list, given only access to that node.

Supposed the linked list is`1 -> 2 -> 3 -> 4`and you are given the third node with value`3`, the linked list should become`1 -> 2 -> 4`after calling your function.

## 题目链接 {#题目链接}

[https://leetcode.com/problems/delete-node-in-a-linked-list/description/](https://leetcode.com/problems/delete-node-in-a-linked-list/description/)

---

# Python

链表的基础操作, 需要注意的是, 题目中给出的某一个中间节点, 需要处理尾节点的问题

```python

# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def deleteNode(self, node):
        """
        :type node: ListNode
        :rtype: void Do not return anything, modify node in-place instead.
        """
        if node is not None:
            node.val = node.next.val
            node.next = node.next.next
```