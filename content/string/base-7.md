# Base 7

## 题目描述

Given an integer, return its base 7 string representation.

**Example 1:**

```text
Input:
 100

Output:
 "202"
```

**Example 2:**

```text
Input:
 -7

Output:
 "-10"
```

**Note:**The input will be in range of \[-1e7, 1e7\].

## 题目链接

[https://leetcode.com/problems/base-7/description/](https://leetcode.com/problems/base-7/description/)

## Java

### 代码

```java
class Solution {
    public String convertToBase7(int num) {
        return Integer.toString(num, 7);
    }
}
```

