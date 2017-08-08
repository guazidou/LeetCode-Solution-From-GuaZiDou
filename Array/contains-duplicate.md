# 问题描述

Given an array of integers, find if the array contains any duplicates. Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

## 题目链接

[https://leetcode.com/problems/contains-duplicate/description/](https://leetcode.com/problems/contains-duplicate/description/)

---

# Python

基本做法,不开额外空间开销, 将数组排序,进行数组元素前后对比

```python
class Solution:
    # @param {integer[]} nums
    # @return {boolean}
    def containsDuplicate(self, nums):
        nums.sort()
        l = len(nums)
        for i in xrange(l-1):
            if nums[i] == nums[i+1]:
                return True
        return False
```

python语言特点做法,提用set集合

```python
class Solution(object):
    def containsDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        return False if len(nums) == len(set(nums)) else True
```

# Java

利用set集合的不可重复性完成本题。

```java
public class Solution {
    public boolean containsDuplicate(int[] nums) {
        Set<Integer> set = new HashSet();
        for (int num : nums) {
            if (!set.add(num)) return true;
        }
        return false;
    }

}
```


