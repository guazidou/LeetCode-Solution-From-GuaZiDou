# 问题描述

Given a sorted integer array without duplicates, return the summary of its ranges.

For example, given`[0,1,2,4,5,7]`, return`["0->2","4->5","7"].`

## 题目链接

[https://leetcode.com/problems/summary-ranges/description/](https://leetcode.com/problems/summary-ranges/description/)

---

# Python

纯模拟题

```python
class Solution:
    # @param {integer[]} nums
    # @return {string[]}
    def summaryRanges(self, nums):
        if nums == []:
            return []
        res = []
        l = len(nums)
        p1 = 0
        p2 = 0
        while p2 < l:
            print nums[p1],nums[p2]
            n = nums[p2] - nums[p2-1]
            if n > 1:
                if nums[p2-1] == nums[p1]:
                    res.append(str(nums[p1]))
                else:
                    res.append(str(nums[p1])+'->'+str(nums[p2-1]))
                p1 = p2
            p2 += 1
        if nums[p2-1] == nums[p1]:
            res.append(str(nums[p1]))
        else:
            res.append(str(nums[p1])+'->'+str(nums[p2-1]))
        return res
```

# Java

```java
public class Solution {
    public List<String> summaryRanges(int[] nums) {
        int last = Integer.MIN_VALUE;
        List<String> result = new ArrayList<>();
        boolean isFirst = true;
        for (int num : nums) {
            if (isFirst) {
                result.add(String.valueOf(num));
                isFirst = false;
            } else if (num == last + 1) {
                String before = result.get(result.size() - 1);
                if (before.contains("->")) {
                    result.set(result.size() - 1, before.split("->")[0] + "->" + num);
                } else {
                    result.set(result.size() - 1, before + "->" + num);
                }
                isFirst = false;
            } else if (num != last + 1) {
                result.add(String.valueOf(num));
            }
            last = num;
        }

        return result;
    }
}
```



