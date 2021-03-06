# Number Complement

## 问题描述

Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary representation.

**Note:**

1. The given integer is guaranteed to fit within the range of a 32-bit signed integer.
2. You could assume no leading zero bit in the integer’s binary representation.

**Example 1:**

```text
Input:
 5

Output:
 2

Explanation:
 The binary representation of 5 is 101 (no leading zero bits), and its complement is 010. So you need to output 2.
```

**Example 2:**

```text
Input:
 1

Output:
 0

Explanation:
 The binary representation of 1 is 1 (no leading zero bits), and its complement is 0. So you need to output 0.
```

## 题目连接

[https://leetcode.com/problems/number-complement/description/](https://leetcode.com/problems/number-complement/description/)

## Python {#python}

python 中~操作是取补码, 此题取反

```python
class Solution(object):
    def findComplement(self, num):
        """
        :type num: int
        :rtype: int
        """
        return num ^ int(bin(num)[2:].replace("0","1"),2)
```

## Java

求没有前导0的正数反码值

```java
class Solution {
    public int findComplement(int num) {
        String s = Integer.toBinaryString(num);
        int result = 0;
        for (int i = s.length() - 1; i >= 0; i--) {
            if (s.charAt(i) == '0') {
                result += Math.pow(2, s.length() - 1 - i);
            }
        }
        return result;
    }
}
```

