# Average of Levels in Binary Tree

## 题目描述

Given a non-empty binary tree, return the average value of the nodes on each level in the form of an array.

**Example 1:**

```text
Input:

    3
   / \
  9  20
    /  \
   15   7

Output:
 [3, 14.5, 11]

Explanation:

The average value of nodes on level 0 is 3,  on level 1 is 14.5, and on level 2 is 11. Hence return [3, 14.5, 11].
```

**Note:**

1. The range of node's value is in the range of 32-bit signed integer.

## 题目链接

[https://leetcode.com/problems/average-of-levels-in-binary-tree/description/](https://leetcode.com/problems/average-of-levels-in-binary-tree/description/)

## Java

### 思路

利用二叉树的层序遍历，在遍历过程中使用辅助列表记录当前遍历层数的元素，最后对辅助列表求平均值即可。

### 代码

```java
class Solution {
    public List<Double> averageOfLevels(TreeNode root) {
        List<List<Integer>> res = new ArrayList<>();
        Queue<TreeNode> q = new LinkedList<>();
        if (root != null) q.offer(root);
        while (!q.isEmpty()) {
            int size = q.size();
            List<Integer> level = new LinkedList<>();
            for (int i = 0; i < size; i++) {
                TreeNode curr = q.poll();
                level.add(curr.val);
                if (curr.left != null) q.offer(curr.left);
                if (curr.right != null) q.offer(curr.right);
            }
            res.add(level);
        }
        List<Double> result = new ArrayList<>();
        for (List<Integer> list : res) {
            result.add(list.stream().mapToInt(i -> i).average().getAsDouble());
        }
        return result;
    }
}
```

