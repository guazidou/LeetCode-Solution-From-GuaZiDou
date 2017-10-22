# 题目描述

Given a positive integernum, write a function which returns True ifnumis a perfect square else False.

**Note:Do not**use any built-in library function such as`sqrt`.

**Example 1:**

```
Input: 16
Returns: True

```



**Example 2:**

```
Input: 14
Returns: False
```

# 题目链接

[https://leetcode.com/problems/valid-perfect-square/description/](https://leetcode.com/problems/valid-perfect-square/description/)

---

# Java

## 代码

```java
class Solution {
    public boolean isPerfectSquare(int num) {
        if (num == 1) return true;
        for (int i = 1; i <= num / 2; i++) {
            if (i * i == num) return true;
            if (i * i > num) return false;
        }
        return false;
    }
}
```



