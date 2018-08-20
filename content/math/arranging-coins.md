# Arranging Coins

## 题目描述

You have a total ofncoins that you want to form in a staircase shape, where everyk-th row must have exactlykcoins.

Givenn, find the total number of**full**staircase rows that can be formed.

nis a non-negative integer and fits within the range of a 32-bit signed integer.

**Example 1:**

```text
n = 5

The coins can form the following rows:
¤
¤ ¤
¤ ¤

Because the 3rd row is incomplete, we return 2.
```

**Example 2:**

```text
n = 8

The coins can form the following rows:
¤
¤ ¤
¤ ¤ ¤
¤ ¤

Because the 4th row is incomplete, we return 3.
```

## 题目链接

[https://leetcode.com/problems/arranging-coins/description/](https://leetcode.com/problems/arranging-coins/description/)

## Java

根据求和公式推导即可

```java
class Solution {
    public int arrangeCoins(int n) {
        return (int) (Math.sqrt(2L * n + 1.0 / 4) - 1.0 / 2);
    }
}
```

