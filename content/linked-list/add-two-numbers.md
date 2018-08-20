# Add Two Numbers

## 问题描述 {#问题描述}

You are given two**non-empty**linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

**Input:**\(2 -&gt; 4 -&gt; 3\) + \(5 -&gt; 6 -&gt; 4\)  
**Output:**7 -&gt; 0 -&gt; 8

### 题目链接 {#题目链接}

[https://leetcode.com/problems/remove-linked-list-elements/\#/description](https://leetcode.com/problems/remove-linked-list-elements/#/description)

## Java

### 思路

涉及到链表的操作，需要考虑进位和两个链表长度不一致的处理。是一个求和的过程，进位+1，单个数值不能超过10。

### Code

```java
public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode result = l1 != null ? l1 : l2;//返回结果
        int carryFlag = 0;//进位
        ListNode last = null;//最后的结点
        while (l1 != null && l2 != null) {
            int val = l1.val + l2.val;
            l1.val = (val + carryFlag) % 10;
            carryFlag = (val + carryFlag) / 10;

            last = l1;
            l1 = l1.next;
            l2 = l2.next;
        }

        while (l1 != null) {
            int val = (l1.val + carryFlag) % 10;
            carryFlag = (l1.val + carryFlag) / 10;
            l1.val = val;

            last.next = l1;
            last = l1;
            l1 = l1.next;
        }

        while (l2 != null) {
            int val = (l2.val + carryFlag) % 10;
            carryFlag = (l2.val + carryFlag) / 10;
            l2.val = val;

            last.next = l2;
            last = l2;
            l2 = l2.next;
        }

        if (carryFlag != 0) {
            last.next = new ListNode(carryFlag);
        }
        return result;
    }
```

## Go

需要注意最后一次加减是否需要进位

### Code

```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func addTwoNumbers(l1 *ListNode, l2 *ListNode) *ListNode {
    res := &ListNode{}
    p, q , w:= l1, l2, res
    var x, y, carry int
    for p != nil || q != nil {
        if p == nil {x = 0} else {x = p.Val}
        if q == nil {y = 0} else {y = q.Val}
        summary := carry + x + y
        carry = summary / 10
        w.Next = &ListNode{summary % 10, nil}
        w = w.Next
        if p != nil {p = p.Next}
        if q != nil {q = q.Next}
    }
    if carry > 0 {
        w.Next = &ListNode{carry, nil}
    }
    return res.Next
}
```

