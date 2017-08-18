# 问题描述

Say you have an array for which theithelement is the price of a given stock on dayi.

Design an algorithm to find the maximum profit. You may complete as many transactions as you like \(ie, buy one and sell one share of the stock multiple times\). However, you may not engage in multiple transactions at the same time \(ie, you must sell the stock before you buy again\).

## 题目链接

[https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/description/](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/description/)

---

# Python

模拟一下

```python
class Solution(object):
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        profit = 0
        for i in xrange(1, len(prices)):
            if prices[i] - prices[i-1] > 0:
                profit = profit + prices[i] - prices[i-1]
        return profit
```


