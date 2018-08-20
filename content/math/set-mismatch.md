# Set Mismatch

## 题目描述

The set`S`originally contains numbers from 1 to`n`. But unfortunately, due to the data error, one of the numbers in the set got duplicated to**another**number in the set, which results in repetition of one number and loss of another number.

Given an array`nums`representing the data status of this set after the error. Your task is to firstly find the number occurs twice and then find the number that is missing. Return them in the form of an array.

**Example 1:**

```text
Input:
 nums = [1,2,2,4]

Output:
 [2,3]
```

**Note:**

1. The given array size will in the range \[2, 10000\].
2. The given array's numbers won't have any order.

## 题目链接

[https://leetcode.com/problems/set-mismatch/description/](https://leetcode.com/problems/set-mismatch/description/)

## Java

题意：有一个数组包含1~n的数，但是数据存在一个重复和一个丢失，分别找出重复和丢失。

```java
class Solution {
       public static int[] findErrorNums(int[] nums) {
        int[] res = new int[2];
        for (int i : nums) {
            if (nums[Math.abs(i) - 1] < 0) res[0] = Math.abs(i);
            else nums[Math.abs(i) - 1] *= -1;
        }
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] > 0) res[1] = i + 1;
        }
        return res;
    }
}
```

