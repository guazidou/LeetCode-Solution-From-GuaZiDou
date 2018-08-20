# Contains Duplicate II

## 问题描述

Given an array of integers and an integer k, find out whether there are two distinct indices i and j in the array such that nums\[i\] = nums\[j\] and the absolute difference between i and j is at most k.

## 题目链接

[https://leetcode.com/problems/contains-duplicate-ii/description/](https://leetcode.com/problems/contains-duplicate-ii/description/)

## Java

题意查找数组中值相同，但是索引差值在k之内。

```java
public class Solution {
    public boolean containsNearbyDuplicate(int[] nums, int k) {
        if (nums.length <= 1) return false;
        Map<Integer, Integer> map = new HashMap();
        for (int i = 0; i < nums.length; i++) {
            if (map.containsKey(nums[i]) && i - map.get(nums[i]) <= k) {
                return true;
            } else {
                map.put(nums[i], i);
            }
        }
        return false;
    }
}
```

