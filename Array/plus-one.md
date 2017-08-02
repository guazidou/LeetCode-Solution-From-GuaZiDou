# 问题描述

Given a non-negative integer represented as a **non-empty **array of digits, plus one to the integer.

You may assume the integer do not contain any leading zero, except the number 0 itself.

The digits are stored such that the most significant digit is at the head of the list.

## 题目链接

[https://leetcode.com/problems/plus-one/description/](https://leetcode.com/problems/plus-one/description/)

---

# Python

Python支持大数加法，直接转换到int型，然后进行字符串处理就好

```python
class Solution:
    # @param {integer[]} digits
    # @return {integer[]}
    def plusOne(self, digits):
        return [int(x) for x in str(int(''.join("%s" % y for y in digits)) + 1)]
```