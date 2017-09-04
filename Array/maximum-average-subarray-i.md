# 题目描述

Given an array consisting of`n`integers, find the contiguous subarray of given length`k`that has the maximum average value. And you need to output the maximum average value.

**Example 1:**  


```
Input:
 [1,12,-5,-6,50,3], k = 4

Output:
 12.75

Explanation:
 Maximum average is (12-5-6+50)/4 = 51/4 = 12.75

```

# 题目链接

[https://leetcode.com/problems/maximum-average-subarray-i/description/](https://leetcode.com/problems/maximum-average-subarray-i/description/)

---



# Java

使用k为滑动窗口，做平均值计算即可。

```java
class Solution {
      public double findMaxAverage(int[] nums, int k) {
        double maxAvg = -Double.MAX_VALUE;
        for (int i = 0; i == 0 || i <= nums.length - k; i++) {
            int sum = 0;
            for (int j = i; j < i + k; j++) {
                sum += nums[j];
            }
            if (maxAvg < sum / (1.0 * k)) {
                maxAvg = sum / (1.0 * k);
            }
        }
        return maxAvg;
    }
}
```



