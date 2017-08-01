# 问题描述

Given an array and a value, remove all instances of that value in place and return the new length.

Do not allocate extra space for another array, you must do this in place with constant memory.

The order of elements can be changed. It doesn't matter what you leave beyond the new length.

**Example:**  
Given input arraynums=`[3,2,2,3]`,val=`3`

Your function should return length = 2, with the first two elements ofnumsbeing 2.

## 题目链接

[https://leetcode.com/problems/remove-element/description/](https://leetcode.com/problems/remove-element/description/)

---

# Python

这是python数组的基本操作，自带了remove，但是一次只删除一个，循环一下删除所有。

```java
class Solution:
    # @param {integer[]} nums
    # @param {integer} val
    # @return {integer}
    def removeElement(self, nums, val):
        while(True):
            try:
                nums.remove(val)
            except ValueError:
                return len(nums)
```

# Java

```java
 public int removeElement(int[] nums, int val) {
        int length = 0;
        for (int num : nums) {
            if (num != val) {
                nums[length++] = num;
            }
        }
        return length;
    }
```



