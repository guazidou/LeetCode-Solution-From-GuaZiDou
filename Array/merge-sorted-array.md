# 问题描述

Given two sorted integer arraysnums1andnums2, mergenums2intonums1as one sorted array.

**Note:**  
You may assume that nums1 has enough space \(size that is greater or equal tom+n\) to hold additional elements from nums2. The number of elements initialized in nums1 and nums2 are m and n respectively.

## 题目链接

[https://leetcode.com/problems/merge-sorted-array/description/](https://leetcode.com/problems/merge-sorted-array/description/)

---

# Python

```python
class Solution:
    # @param {integer[]} nums1
    # @param {integer} m
    # @param {integer[]} nums2
    # @param {integer} n
    # @return {void} Do not return anything, modify nums1 in-place instead.
    def merge(self, nums1, m, nums2, n):
        nums1[m:] = nums2[:n]
        nums1.sort()
```