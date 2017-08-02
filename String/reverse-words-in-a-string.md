# 问题描述

Given an input string, reverse the string word by word.

For example,  
Given s = "`the sky is blue`",  
return "`blue is sky the`".

**Update \(2015-02-12\):**  
For C programmers: Try to solve itin-placeinO\(1\) space.

[click to show clarification.](https://leetcode.com/problems/reverse-words-in-a-string/description/#)

## 题目链接

[https://leetcode.com/problems/reverse-words-in-a-string/description/](https://leetcode.com/problems/reverse-words-in-a-string/description/)

---

# Python

string的常见操作，先将字符串以空格分割，然后逆序合并

```python
class Solution:
    # @param s, a string
    # @return a string
    def reverseWords(self, s):
        return ' '.join(s.split()[::-1])
```

# Java

```java
public class Solution {
    public String reverseWords(String s) {
        return Stream.of(s.trim().split("\\s+")).sorted((x, y) -> -1).collect(Collectors.joining(" "));
    }
}
```



