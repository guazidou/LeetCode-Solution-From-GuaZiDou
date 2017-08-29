# 问题描述

The [Hamming distance](https://en.wikipedia.org/wiki/Hamming_distance) between two integers is the number of positions at which the corresponding bits are different.

Given two integers`x`and`y`, calculate the Hamming distance.

**Note:**  
0 ≤`x`,`y`&lt; 231.

**Example:**

```
Input:
 x = 1, y = 4


Output:
 2


Explanation:

1   (0 0 0 1)
4   (0 1 0 0)
       ↑   ↑

The above arrows point to positions where the corresponding bits are different.
```

# 题目连接

[https://leetcode.com/problems/hamming-distance/description/](https://leetcode.com/problems/hamming-distance/description/)

---

# Python {#python}

与后，计算1数？

```python
class Solution(object):
    def hammingDistance(self, x, y):
        """
        :type x: int
        :type y: int
        :rtype: int
        """
        return str(bin(x ^ y)).count("1")
```

