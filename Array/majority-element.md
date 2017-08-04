# 问题描述

Given an array of sizen, find the majority element. The majority element is the element that appears **more than**`⌊ n/2 ⌋`times.

You may assume that the array is non-empty and the majority element always exist in the array.

## 题目链接

[https://leetcode.com/problems/majority-element/description/](https://leetcode.com/problems/majority-element/description/)

---

# Python

找出数组中出现次数多于n/2，暴力直接过了

```python
class Solution:
    # @param {integer[]} nums
    # @return {integer}
    def majorityElement(self, nums):
        n = len(nums)
        s = set(nums)
        for i in s:
            if nums.count(i) > n/2:
                return i
```

# Java

既然要找出现次数大于n/2,可以先排序，然后取索引为n/2的值即为本题的结果。

```java
public class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        return nums[nums.length / 2];
    }

}
```



