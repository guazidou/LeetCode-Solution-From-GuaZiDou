# 题目描述


Given an array of integers where 1 ≤ a\[i\] ≤n\(n= size of array\), some elements appear twice and others appear once.

Find all the elements of \[1,n\] inclusive that do not appear in this array.

Could you do it without extra space and in O\(n\) runtime? You may assume the returned list does not count as extra space.

**Example:**

```
Input:

[4,3,2,7,8,2,3,1]


Output:

[5,6]

```

# 题目链接

[https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/description/](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/description/)

---

# Python

遍历每一个值, 标记其所指下标的值为负, 检查负值即可

```python
class Solution(object):
    def findDisappearedNumbers(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        for i in xrange(len(nums)):
            nums[abs(nums[i]) - 1] = - abs(nums[abs(nums[i]) - 1])

        return [i + 1 for i in range(len(nums)) if nums[i] > 0]
```