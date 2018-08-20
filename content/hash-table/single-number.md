# Single Number

## 问题描述

Given an array of integers, every element appearstwiceexcept for one. Find that single one.

**Note:**  
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

### 题目链接

[https://leetcode.com/problems/single-number/\#/description](https://leetcode.com/problems/single-number/#/description)

## Python

遍历

```python
class Solution:
    # @param {integer[]} nums
    # @return {integer}
    def singleNumber(self, nums):
        l = len(nums)
        nums = sorted(nums)
        for i in xrange(0, l-1, 2):
            if nums[i] - nums[i+1] != 0:
                return nums[i] if nums[i+1] - nums[i+1] == 0 else nums[i+1]
        return nums[l-1]
```

遍历, 亦或

```python
class Solution:
    # @param {integer[]} nums
    # @return {integer}
    def singleNumber(self, nums):
        num = 0
        for i in nums:
            num ^= i
        return num
```

函数式

```python
class Solution:
    # @param {integer[]} nums
    # @return {integer}
    def singleNumber(self, nums):
        return reduce(lambda x, y:x^y,nums)
```

## Java

```java
public int singleNumber(int[] nums) {
        int singleNum = 0;
        for (int i = 0; i < nums.length; i++) {
            singleNum ^= nums[i];
        }
        return singleNum;
    }
```

