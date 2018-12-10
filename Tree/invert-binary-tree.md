# 问题描述

Invert a binary tree.

```
     4
   /   \
  2     7
 / \   / \
1   3 6   9
```

to

```
     4
   /   \
  7     2
 / \   / \
9   6 3   1
```

## 题目连接

[https://leetcode.com/problems/invert-binary-tree/description/](https://leetcode.com/problems/invert-binary-tree/description/)

---

# Python {#python}

二叉树翻转使用基本的递归可解决

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def invertTree(self, root):
        """
        :type root: TreeNode
        :rtype: TreeNode
        """
        if root is None:
            return
        root.left, root.right = root.right, root.left
        self.invertTree(root.left)
        self.invertTree(root.right)
        return root
```

# Java

利用递归的思想依次交换左右节点

```java
public class Solution {
    public TreeNode invertTree(TreeNode root) {
        if (root == null)
            return null;
        TreeNode tmp = root.left;
        root.left = root.right;
        root.right = tmp;

        root.left = invertTree(root.left);
        root.right = invertTree(root.right);
        return root;
    }
}
```



# Golang


```golang
func InvertTree(root *TreeNode) {
	if root == nil {
		return
	}

	root.Left, root.Right = root.Right, root.Left

	InvertTree(root.Left)
	InvertTree(root.Right)
}
```
