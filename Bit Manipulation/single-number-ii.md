# 问题描述

Given an array of integers, every element appearsthreetimes except for one, which appears exactly once. Find that single one.

**Note:**
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

题目连接

[https://leetcode.com/problems/single-number-ii/description/](https://leetcode.com/problems/single-number-ii/description/)

---

# Python {#python}

需要实现一个3次计数, 

```python
class Solution:
    # @param {integer[]} nums
    # @return {integer}
    def singleNumber(self, nums):
        x, y = 0, 0
        for num in nums:
            x = (x ^ num) & (~y)
            y = (y ^ num) & (~x)
        return x

```