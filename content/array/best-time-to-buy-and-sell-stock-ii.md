# Best Time to Buy and Sell Stock II

## 问题描述

Say you have an array for which the lement is the price of a given stock on day.

Design an algorithm to find the maximum profit. You may complete as many transactions as you like \(ie, buy one and sell one share of the stock multiple times\). However, you may not engage in multiple transactions at the same time \(ie, you must sell the stock before you buy again\).

### 题目链接

[https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/description/](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/description/)

## Python

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

## Golang

```go
package main

import (
    "fmt"
)

func MaxProfit(price []int) int {
    profit := 0
    for i := 1; i < len(price); i++ {
        if price[i] > price[i-1] {
            profit += price[i] - price[i-1]
        }
    }
    return profit
}

func main() {
    prices := []int{3, 4, 2, 1, 3, 5, 6}
    fmt.Println(MaxProfit(prices))
}
```

