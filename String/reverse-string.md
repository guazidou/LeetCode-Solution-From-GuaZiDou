# 问题描述

Write a function that takes a string as input and returns the string reversed.

**Example:**  
Given s = "hello", return "olleh".

题目连接: [https://leetcode.com/problems/reverse-string/](https://leetcode.com/problems/reverse-string/)

# Python {#python}

使用python字符串强大的切片解决

```py
class Solution(object):
    def reverseString(self, s):
        """
        :type s: str
        :rtype: str
        """
        return s[::-1]
```

# JavaScript

```js
/**
 * @param {string} s
 * @return {string}
 */
var reverseString = function(s) {
    return s.split("").reverse().join("")
};
```

# Go

```go
func reverseString(s string) string {
    runes := []rune(s)
    for i, j := 0, len(runes)-1; i < j; i, j = i+1, j-1 {
        runes[i], runes[j] = runes[j], runes[i]
    }
    return string(runes)
}
```



