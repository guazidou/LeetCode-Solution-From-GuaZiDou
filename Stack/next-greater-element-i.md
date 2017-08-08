# 问题描述

You are given two arrays**\(without duplicates\)**`nums1`and`nums2`where`nums1`’s elements are subset of`nums2`. Find all the next greater numbers for`nums1`'s elements in the corresponding places of`nums2`.

The Next Greater Number of a number**x**in`nums1`is the first greater number to its right in`nums2`. If it does not exist, output -1 for this number.

# 题目链接

[https://leetcode.com/problems/next-greater-element-i/description/](https://leetcode.com/problems/next-greater-element-i/description/)

---

# Java

题目说明两个数组不包含重复数据，nums1是nums2的子集，让求nums1中个元素在nums2中的下一个更大的元素值，不存在返回-1.思路：可以利用栈来解决本题，先将nums2倒序放入栈中，依次查找nums1中元素的更大值，将上述的栈拷贝一份不影响下次处理，弹出栈顶元素若与nums1中当前查找的元素值相同置标志位，若标志位已置且栈顶值大于nums1当前查找的元素则代表该值为更大的值。

```java
public class Solution {
    public int[] nextGreaterElement(int[] findNums, int[] nums) {
        Stack<Integer> stack = new Stack<>();
        for (int i = nums.length - 1; i >= 0; i--) {
            stack.push(nums[i]);
        }

        int[] result = new int[findNums.length];
        int i = 0;
        for (int findNum : findNums) {
            result[i++] = findGreater(findNum, stack);
        }
        return result;
    }

    int findGreater(int findNum, Stack<Integer> stack) {
        Stack<Integer> stackClone = (Stack<Integer>) stack.clone();
        boolean isFindNum = false;
        while (!stackClone.isEmpty()) {
            int num = stackClone.pop();
            if (num == findNum) {
                isFindNum = true;
            }
            if (isFindNum && num > findNum) {
                return num;
            }
        }
        return -1;
    }
}
```



