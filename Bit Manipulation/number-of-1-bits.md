# 问题描述

Write a function that takes an unsigned integer and returns the number of ’1' bits it has \(also known as the[Hamming weight](http://en.wikipedia.org/wiki/Hamming_weight)\).

For example, the 32-bit integer ’11' has binary representation`00000000000000000000000000001011`, so the function should return 3.

  
题目连接

[https://leetcode.com/problems/number-of-1-bits/description/](https://leetcode.com/problems/number-of-1-bits/description/)

---

# Python {#python}

```python
class Solution(object):
    def hammingWeight(self, n):
        """
        :type n: int
        :rtype: int
        """
        return bin(n).count('1')
```



