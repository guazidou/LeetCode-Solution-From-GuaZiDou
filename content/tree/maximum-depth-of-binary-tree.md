# Maximum Depth of Binary Tree

## 问题描述

Given a binary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

### 题目连接

[https://leetcode.com/problems/maximum-depth-of-binary-tree/description/](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)

## Python {#python}

树的基本操作, 最大深度, 递归算法

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def maxDepth(self, root):
        """
        :type root: TreeNode
        :rtype: int
        """
        l = 0
        if root is not None:
            left = self.maxDepth(root.left)
            right = self.maxDepth(root.right)
            l = left + 1 if left >= right else right + 1
        return l
```

## Java

```java
public class Solution {
    public int maxDepth(TreeNode root) {
        if (root == null)
            return 0;
        int leftDepth = maxDepth(root.left);
        int rightDepth = maxDepth(root.right);
        return leftDepth >= rightDepth ? leftDepth + 1 : rightDepth + 1;
    }
}
```

