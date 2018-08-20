# Non-decreasing Array

## 题目描述

Given an array with`n`integers, your task is to check if it could become non-decreasing by modifying**at most**`1`element.

We define an array is non-decreasing if`array[i] <= array[i + 1]`holds for every`i`\(1 &lt;= i &lt; n\).

## 题目链接

[https://leetcode.com/problems/non-decreasing-array/description/](https://leetcode.com/problems/non-decreasing-array/description/)

## Java

题意要求判断数组是否满足最多修改一个元素的前提下保证是非递减的。

```java
class Solution {
      public boolean checkPossibility(int[] nums) {
        int count = 0;
        for (int i = 1; i < nums.length; i++) {
            if (nums[i - 1] > nums[i]) {
                count++;
                if (i - 2 < 0 || nums[i - 2] < nums[i]) nums[i - 1] = nums[i];
                else nums[i] = nums[i - 1];
            }
        }
        return count <= 1;
    }

}
```

