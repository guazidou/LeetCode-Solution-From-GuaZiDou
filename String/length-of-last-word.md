# 问题描述

Given a stringsconsists of upper/lower-case alphabets and empty space characters`' '`, return the length of last word in the string.

If the last word does not exist, return 0.

**Note:**A word is defined as a character sequence consists of non-space characters only.

For example,  
Givens=`"Hello World"`,  
return`5`.

## 题目链接

[https://leetcode.com/problems/length-of-last-word/description/](https://leetcode.com/problems/length-of-last-word/description/)

---

# Python

python强大的字符串处理能力，直接可以已空格划分，pop出最后一个字串测量长度，处理一下空字符串问题

```python
class Solution:
    # @param {string} s
    # @return {integer}
    def lengthOfLastWord(self, s):
        try:
            l = len(s.split().pop())
        except IndexError:
            l = 0
        finally:
            return l
```

# Java

按空格分割，求最后一个字符串的长度

```java
public class Solution {
    public int lengthOfLastWord(String s) {
        return s.trim().split(" ")[s.trim().split(" ").length - 1].length();
    }
}
```


# Go
```
package main

import (
	"fmt"
	"strings"
)

func lenOfLastWord(word string) int {
	words := strings.Fields(word)
	last_word := words[len(words)-1]
	return len(last_word)
}

func main() {
	fmt.Println(lenOfLastWord("hello world, hello golang."))
}
```
