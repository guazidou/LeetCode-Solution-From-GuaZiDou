# Merge Sorted Array

## 问题描述

Given two sorted integer arraysnums1andnums2, mergenums2intonums1as one sorted array.

**Note:**  
You may assume that nums1 has enough space \(size that is greater or equal tom+n\) to hold additional elements from nums2. The number of elements initialized in nums1 and nums2 are m and n respectively.

### 题目链接

[https://leetcode.com/problems/merge-sorted-array/description/](https://leetcode.com/problems/merge-sorted-array/description/)

## Python

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

## Java

两个数组本身已经排好序，现在从2个数组的末尾开始比较，将大的结果放到nums1末尾，并将索引-1，依次到nums1全部占满。

```java
public class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int p = m + n, p1 = m - 1, p2 = n - 1;
        while (--p >= 0) {
            if ((p2 < 0) || (p1 >= 0 && nums1[p1] >= nums2[p2])) {
                nums1[p] = nums1[p1--];
            } else {
                nums1[p] = nums2[p2--];
            }
        }
    }
}
```

