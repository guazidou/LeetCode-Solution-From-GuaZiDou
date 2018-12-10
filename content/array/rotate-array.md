# Rotate Array

## 问题描述

Rotate an array of _**n**_ elements to the right by _**k**_ steps.

For example, withn= 7 andk= 3, the array`[1,2,3,4,5,6,7]`is rotated to`[5,6,7,1,2,3,4]`.

### 题目链接

[https://leetcode.com/problems/pascals-triangle/\#/description](https://leetcode.com/problems/pascals-triangle/#/description)

## Python

### 思路

题目中n个元素其实是指数组的长度为n，轮转k步可以理解为n对k求余，按余数将数组尾部截取到数组头部。利用pyhon切片可以快速解决。

```python
class Solution:
    # @param {integer[]} nums
    # @param {integer} k
    # @return {void} Do not return anything, modify nums in-place instead.
    def rotate(self, nums, k):
        l = len(nums)
        nums[:] = nums[l-k:l] + nums[0:l-k]
```

## Golang

通过三次reverse实现, 原地修改

```golang
func rotate(nums []int, k int){
    reverse(nums[:k+1])
    reverse(nums[k+1:])
    reverse(nums)
}

func reverse(nums []int){
    l := len(nums)
    for i := 0; i < l / 2; i++ {
        nums[i], nums[l - 1 - i] = num[l - 1 - i], num[i]
    }
}
```
