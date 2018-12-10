# 问题描述

Given a binary search tree \(BST\), find the lowest common ancestor \(LCA\) of two given nodes in the BST.

According to the[definition of LCA on Wikipedia](https://en.wikipedia.org/wiki/Lowest_common_ancestor): “The lowest common ancestor is defined between two nodes v and w as the lowest node in T that has both v and w as descendants \(where we allow**a node to be a descendant of itself**\).”

```
        _______6______
       /              \
    ___2__          ___8__
   /      \        /      \
   0      _4       7       9
         /  \
         3   5
```

For example, the lowest common ancestor \(LCA\) of nodes`2`and`8`is`6`. Another example is LCA of nodes`2`and`4`is`2`, since a node can be a descendant of itself according to the LCA definition.

## 题目连接

[https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/description/](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/description/)

---

# Python {#python}

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def lowestCommonAncestor(self, root, p, q):
        """
        :type root: TreeNode
        :type p: TreeNode
        :type q: TreeNode
        :rtype: TreeNode
        """
        if p.val > q.val:
            p, q = q, p
        while root.val < p.val or root.val > q.val:
            if root.val > q.val:
                root = root.left
                continue
            if root.val < p.val:
                root = root.right
                continue
            if root.val == p.val:
                return root
            if root.val == q.val:
                return root
        return root
```

# Java

经典的最近祖先算法，先让节点p，q按小到大排序，然后从根节点满足根节点值小于p值或大于q值开始循环，若根节点值小于p值，根节点取其右节点，若根节点值大于q值，根节点取其左节点。

```java
class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if (p.val > q.val) {
            TreeNode tmp = p;
            p = q;
            q = tmp;
        }
        while (root.val < p.val || root.val > q.val) {
            if (root.val < p.val) {
                root = root.right;
            }
            if (root.val > q.val) {
                root = root.left;
            }
        }
        return root;
    }
}
```


# Golang

```Golang
func lowestCommonAncestor(root *TreeNode, p *TreeNode, q *TreeNode) *TreeNode{
  if p.Val > q.Val {
    p, q = q, p
  }

  for root.Val < p.Val || root.Val > q.Val {
    if root.Val < p.Val {
      root = root.Right
    }
    if root.Val > q.Val {
      root = root.Left
    }
  }
  return root
}
```
