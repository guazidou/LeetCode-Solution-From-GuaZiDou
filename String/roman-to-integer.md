# 问题描述

Given a roman numeral, convert it to an integer.

Input is guaranteed to be within the range from 1 to 3999.

## 题目连接

[https://leetcode.com/problems/roman-to-integer/\#/description](https://leetcode.#/problems/roman-to-integer/#/description)

---

# 罗马数字

从1到10的罗马数字:

```
**I, II, III, IV, V, VI, VII, VIII, IX, X**
```

| Symbol | [I](https://en.wikipedia.org/wiki/I) | [V](https://en.wikipedia.org/wiki/V) | [X](https://en.wikipedia.org/wiki/X) | [L](https://en.wikipedia.org/wiki/L) | [C](https://en.wikipedia.org/wiki/C) | [D](https://en.wikipedia.org/wiki/D) | [M](https://en.wikipedia.org/wiki/M) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Value | 1 | 5 | 10 | 50 | 100 | 500 | 1,000 |

# Python {#python}

## 解题思路

罗马数字只有一个坑,如果下一个罗马数字比前一个大,是需要减去

## 代码

```py
class Solution(object):
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """
        roman = dict(I=1,V=5,X=10,L=50,C=100,D=500,M=1000)
        res = 0
        for i in range(len(s)-1):
            if roman[s[i]] < roman[s[i+1]]:
                res -= roman[s[i]]
            else:
                res += roman[s[i]]
        return res + roman[s[len(s)-1]]
```

# Java

```java
public int romanToInt(String s) {
        int result = 0;
        HashMap<String, Integer> roman = new HashMap() {
            {
                put("I", 1);
                put("V", 5);
                put("X", 10);
                put("L", 50);
                put("C", 100);
                put("D", 500);
                put("M", 1000);

            }
        };
        for (int i = 0; i < s.length(); i++) {
            if (i == s.length() - 1) {
                return result + roman.get("" + s.charAt(i));
            }
            if (roman.get("" + s.charAt(i)) >= roman.get("" + s.charAt(i + 1))) {
                result += roman.get("" + s.charAt(i));
            } else {
                result -= roman.get("" + s.charAt(i));
            }
        }
        return result;
    }
```



