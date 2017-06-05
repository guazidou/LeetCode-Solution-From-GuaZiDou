# 问题描述

Write a function that takes a string as input and returns the string reversed.

**Example:**  
Given s = "hello", return "olleh".

题目连接: [https://leetcode.com/problems/reverse-string/](https://leetcode.com/problems/reverse-string/)

# Python {#python}

## 解题思路

使用python字符串强大的切片解决

## 代码

```py
class Solution(object):
    def reverseString(self, s):
        """
        :type s: str
        :rtype: str
        """
        return s[::-1]
```



