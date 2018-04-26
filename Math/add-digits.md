# 问题描述

Given a non-negative integer\(\)m\`, repeatedly add all its digits until the result has only one digit.

For example:

Given`num = 38`, the process is like:`3 + 8 = 11`,`1 + 1 = 2`. Since`2`has only one digit, return it.

## 题目连接

[https://leetcode.com/problems/add-digits/description/](https://leetcode.com/problems/add-digits/description/)

---

# Python {#python}

树根问题  
[https://en.wikipedia.org/wiki/Digital\_root\#Congruence\_formula](https://en.wikipedia.org/wiki/Digital_root#Congruence_formula)

python 求余定义问题  
[https://docs.python.org/3/reference/expressions.html\#binary-arithmetic-operations](https://docs.python.org/3/reference/expressions.html#binary-arithmetic-operations)

```python
class Solution(object):
    def addDigits(self, num):
        """
        :type num: int
        :rtype: int
        """
        return 0 if num == 0 else 1 + (num - 1) % 9
```

# Java

```java
public class Solution {
    public int addDigits(int num) {
        return num == 0 ? 0 : 1 + (num - 1) % 9;
    }
}
```

# golang

```golang
func AddDigits(num int){
    if num == 0{
        return 0
    }else{
        return 1 + (num - 1) % 9;
    }
}
```



