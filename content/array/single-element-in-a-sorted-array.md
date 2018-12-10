# Single Element in a Sorted Array

## 题目描述

Given a sorted array consisting of only integers where every element appears twice except for one element which appears once. Find this single element that appears only once.

**Example 1:**

```text
Input:
 [1,1,2,3,3,4,4,8,8]

Output:
 2
```

**Example 2:**

```text
Input:
 [3,3,7,7,10,11,11]

Output:
 10
```

**Note:**Your solution should run in O\(log n\) time and O\(1\) space.

## 题目链接

[https://leetcode.com/problems/single-element-in-a-sorted-array/description/](https://leetcode.com/problems/single-element-in-a-sorted-array/description/)

## Python
XXX O\(log n\) 未满足

出现两次的数亦或为0

```python
class Solution(object):
    def singleNonDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        return reduce(lambda x, y: x^y ,nums)
```


## Golang

TODO 未调试,下面是伪码
二分查找, 包含single-element的部分长度一定为奇数.

```golang
func singleNonDuplicate(nums []int) int{
    l = len(nums)
    return find(nums, 0, l-1)
}

func find(nums []int, start int, end int) int{
    mid = (end - start + 1) / 2
    if end - start == 2 {
       # TODO 
    }
    if nums[mid] != nums[mid-1] && nums[mid] != nums[mid+1]{
        return nums[mid]
    }
    if nums[mid] == nums[mid-1] {
        if isodd(mid - start - 1){
            return find(nums, mid, end)
        }else{
            return find(nums, start, mid - 1)
        }
    }
    if nums[mid] == nums[mid+1] {
        if isodd(end - mid) {
            return find(nums, start, mid)
        }else{
            return find(nums, mid+1, end)
        }
    }
}

func isodd(n int) bool {
    return n % 2 == 0
}
```
