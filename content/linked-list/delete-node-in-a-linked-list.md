# Delete Node in a Linked List

## 问题描述 {#问题描述}

Write a function to delete a node \(except the tail\) in a singly linked list, given only access to that node.

Supposed the linked list is`1 -> 2 -> 3 -> 4`and you are given the third node with value`3`, the linked list should become`1 -> 2 -> 4`after calling your function.

### 题目链接 {#题目链接}

[https://leetcode.com/problems/delete-node-in-a-linked-list/description/](https://leetcode.com/problems/delete-node-in-a-linked-list/description/)

## Python

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

## Java

题意：给出一个非尾节点并进行删除，简单的将被删除的节点的值被赋予下个节点的值，它的下个节点成为下下个节点即可。

```java
public class Solution {
    public void deleteNode(ListNode node) {
        if (node != null) {
            node.val = node.next.val;
            node.next = node.next.next;
        }
    }
}
```


## golang

无法取得前节点在删除的情况下,将当前节点Val和Next指针替换为下个节点

```golang
//type ListNode struct {
//  Val  int
//  Next *ListNode
//}

func deleteNode(node *ListNode) {
    if node != nil {
        node.Val = node.Next.Val
        node.Next = node.Next.Next
    }
}
```
