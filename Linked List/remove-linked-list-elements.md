# 问题描述

Remove all elements from a linked list of integers that have value**val**.

**Example**  
**Given:**1 --&gt; 2 --&gt; 6 --&gt; 3 --&gt; 4 --&gt; 5 --&gt; 6,**val**= 6  
**Return:**1 --&gt; 2 --&gt; 3 --&gt; 4 --&gt; 5

## 题目链接

[https://leetcode.com/problems/remove-linked-list-elements/\#/description](https://leetcode.com/problems/remove-linked-list-elements/#/description)

---

# Python

## 思路

单向链表的删除操作,基础题目

## code

```py
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def removeElements(self, head, val):
        """
        :type head: ListNode
        :type val: int
        :rtype: ListNode
        """
        work = head
        prior = None
        while work is not None:
            if work.val == val:
                if prior is None:
                    head = work.next
                else:
                    prior.next = work.next
            else:
                prior = work
            work = work.next
        return head
```

# Java

```java
public static ListNode removeElements(ListNode head, int val) {
        ListNode pre = new ListNode(Integer.MAX_VALUE);
        pre.next = head;
        ListNode result = pre;
        ListNode now = head;
        while (now != null) {
            if (now.val == val) {
                pre.next = now.next;
                now = pre.next;
            } else {
                pre = pre.next;
                now = now.next;
            }
        }
        return result.next;
    }
```


# Golang

需要考虑root可能需要被删除的情况.

```golang
//type ListNode struct {
//  Val  int
//  Next *ListNode
//}


func removeElements(root *ListNode, val int) {
    pre := &ListNode{
        Next: root,
    }
    cur := root
    for cur != nil {
        if cur.Val == val {
            pre.next = now.next
            now = pre.next
        } else {
            pre = pre.next
            now = now.next
        }
    }
    return pre.Next
}
```