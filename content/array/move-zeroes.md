# Move Zeroes

## 问题描述

Given an array`nums`, write a function to move all`0`'s to the end of it while maintaining the relative order of the non-zero elements.

For example, given`nums = [0, 1, 0, 3, 12]`, after calling your function,`nums`should be`[1, 3, 12, 0, 0]`.

**Note**:

1. You must do this

   **in-place**

   without making a copy of the array.

2. Minimize the total number of operations.

### 题目链接

[https://leetcode.com/problems/move-zeroes/description/](https://leetcode.com/problems/move-zeroes/description/)

## Python

将0移到尾部，交换操作

```python
class Solution(object):
    def moveZeroes(self, nums):
        """
        :type nums: List[int]
        :rtype: void Do not return anything, modify nums in-place instead.
        """
        l = len(nums)
        i = 0
        while i < l:
            if nums[i] == 0:
                nums.append(nums.pop(i))
                l -= 1
            else:
                i += 1
```

## Java

利用冒泡思想将0堆到尾部

```java
public class Solution {
    public void moveZeroes(int[] nums) {
        boolean isFinish = true;
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] == 0 && i != nums.length - 1) {
                if (nums[i + 1] != 0) {
                    isFinish = false;
                }
                int tmp = nums[i];
                nums[i] = nums[i + 1];
                nums[i + 1] = tmp;

            }
        }
        if (!isFinish) moveZeroes(nums);
    }
}
```

