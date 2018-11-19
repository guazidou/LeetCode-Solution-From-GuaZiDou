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

# Java

```java
class Solution {
    public List<Integer> findDisappearedNumbers(int[] nums) {
        List<Integer> result = new ArrayList<>();
        for (int num : nums) {
            nums[Math.abs(num) - 1] = -Math.abs(Math.abs(nums[Math.abs(num) - 1]));
        }
        for (int i = 1; i <= nums.length; i++) {
            if (nums[i - 1] > 0) result.add(i);
        }
        return result;
    }
}
```

# golang

```golang
func findDiappearedNumbers(nums []int) result []int{
    for index, value := range nums{
        nums[abs(nums[index]) - 1] = - abs(nums[abs(nums[i]]) - 1)
    }

    for _, value = range nums {
        if value > 0 {
            result := append(result, value)
        }
    }
    return result
}

func abs(a int) int{
    if a >= 0 {
        return a
    }
    return -a
}
```

