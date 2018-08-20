# Single Element in a Sorted Array

## 题目描述

Given a sorted array consisting of only integers where every element appears twice except for one element which appears once. Find this single element that appears only once.

**Example 1:**

```text
Input:
 [1,1,2,3,3,4,4,8,8]

Output:
 2
```

**Example 2:**

```text
Input:
 [3,3,7,7,10,11,11]

Output:
 10
```

**Note:**Your solution should run in O\(log n\) time and O\(1\) space.

## 题目链接

[https://leetcode.com/problems/single-element-in-a-sorted-array/description/](https://leetcode.com/problems/single-element-in-a-sorted-array/description/)

## Python

出现两次的数亦或为0

```python
class Solution(object):
    def singleNonDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        return reduce(lambda x, y: x^y ,nums)
```

