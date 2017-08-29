# 问题描述

Given an array of integers, return **indices **of the two numbers such that they add up to a specific target.

You may assume that each input would have **exactly **one solution, and you may not use the same element twice.

**Example:**

```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

## 题目链接

[https://leetcode.com/problems/two-sum/description/](https://leetcode.com/problems/two-sum/description/)

---

# Python

两个指针

```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        for i in xrange(len(nums)-1):
            for j in xrange(i+1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]
```

两个指针

```python
class Solution:
    # @param {integer[]} nums
    # @param {integer} target
    # @return {integer[]}
    def twoSum(self, nums, target):
        sortedNums = sorted(nums)
        index1 = 0
        index2 = len(nums) - 1
        while index1 <= index2 :
            if sortedNums[index1] + sortedNums[index2] > target:
                index2 -= 1
            elif sortedNums[index1] + sortedNums[index2] < target:
                index1 += 1
            else:
                break
        return sorted([nums.index(sortedNums[index1])+1,nums.index(sortedNums[index2])+1])
```

# Java

循环即可解决

```java
public class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] results = new int[2];
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                    results[0] = i;
                    results[1] = j;
                    return results;
                }
            }
        }
        return results;
    }
}
```



