# 问题描述

Say you have an array for which the ith element is the price of a given stock on day i.

If you were only permitted to complete at most one transaction \(ie, buy one and sell one share of the stock\), design an algorithm to find the maximum profit.

**Example 1:**

```
Input: [7, 1, 5, 3, 6, 4]
Output: 5

max. difference = 6-1 = 5 (not 7-1 = 6, as selling price needs to be larger than buying price)
```

**Example 2:**

```
Input: [7, 6, 4, 3, 1]
Output: 0

In this case, no transaction is done, i.e. max profit = 0.
```

## 题目链接

[https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)

---

# Python

DP的入门题目,先用模拟做

```python
class Solution(object):
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        import sys
        lowprice = sys.maxint
        profit = 0
        for price in prices:
            if price < lowprice:
                lowprice = price
            if price - lowprice > profit:
                profit = price -lowprice
        return profit
```

# Java

暴力求解

```java
class Solution {
    public int maxProfit(int[] prices) {
        int max = 0;
        int curMin = Integer.MAX_VALUE;
        for (int i = 0; i < prices.length; i++) {
            curMin = Math.min(curMin, prices[i]);
            max = Math.max(max, prices[i] - curMin);
        }
        return max;
    }
}
```



