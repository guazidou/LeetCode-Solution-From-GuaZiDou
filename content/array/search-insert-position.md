# Search Insert Position

## 问题描述

Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You may assume no duplicates in the array.

Here are few examples.  
`[1,3,5,6]`, 5 → 2  
`[1,3,5,6]`, 2 → 1  
`[1,3,5,6]`, 7 → 4  
`[1,3,5,6]`, 0 → 0

## 题目链接

[https://leetcode.com/problems/search-insert-position/description/](https://leetcode.com/problems/search-insert-position/description/)

## Java

```java
class Solution {
    public int searchInsert(int[] nums, int target) {
        int i = 0;
        for (int num : nums) {
            if (num == target) return i;
            else if (target < num) return i;
            i++;
        }
        return nums.length ;
    }
}
```


## golang
简单遍历

```golang
func searchInsert(nums []int, target int) int{
   for i, v := range nums {
     if target <= v{
         return i
     }
   } 
   return len(nums)
}
```
