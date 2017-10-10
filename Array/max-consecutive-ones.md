# 题目描述

Given a binary array, find the maximum number of consecutive 1s in this array.

**Example 1:**  


```
Input:
 [1,1,0,1,1,1]

Output:
 3

Explanation:
 The first two digits or the last three digits are consecutive 1s.
    The maximum number of consecutive 1s is 3.

```



**Note:**

* The input array will only contain `0` and `1`.
* The length of input array is a positive integer and will not exceed 10,000

# 题目链接

[https://leetcode.com/problems/max-consecutive-ones/description/](https://leetcode.com/problems/max-consecutive-ones/description/)

---



# Python
遍历一遍,找出最大连续的1

one line solution 
```python
max(map(len, ''.join([str(i) for i in nums]).split('0')))
```

traverse

```python
class Solution(object):
    def findMaxConsecutiveOnes(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        ml = 0
        tl = 0
        for i in nums:
            if i:
                tl += 1
            else:
                max(ml,tl)
                tl = 0
        if tl > ml:
            return tl
        else:
            return ml
```