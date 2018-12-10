# Same Tree

## 问题描述

Given two binary trees, write a function to check if they are equal or not.

Two binary trees are considered equal if they are structurally identical and the nodes have the same value.

### 题目连接

[https://leetcode.com/problems/same-tree/description/](https://leetcode.com/problems/same-tree/description/)

## Python {#python}

模拟

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def isSameTree(self, p, q):
        """
        :type p: TreeNode
        :type q: TreeNode
        :rtype: bool
        """
        if p is None and q is None:
            return True
        if p is None and q is not None or p is not None and q is None:
            return False
        if p.val == q.val and self.isSameTree(p.left, q.left) and self.isSameTree(p.right, q.right):
            return True
        else:
            return False
```

## Java

递归比较即可

```java
public class Solution {
    public boolean isSameTree(TreeNode p, TreeNode q) {
        if (p == null && q == null) return true;
        if ((p == null && q != null) || (p != null && q == null)) return false;
        if (p.val != q.val) return false;
        return isSameTree(p.left,q.left) && isSameTree(p.right,q.right);
    }
}
```


# Golang

```Golang
func isSameTree(p *NodeTree, q *NodeTree) bool {
  if p == nil && q == nil {
    return true
  }
  if (p != nil && q == nil) || (p == nil && q != nil){
    return false
  }

  if p.Val != q.Val {
    return False
  }

  return isSameTree(p.Left, q.Left) && isSameTree(p.Right, q.Right)
}
```
