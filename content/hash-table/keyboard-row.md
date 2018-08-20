# Keyboard Row

## 问题描述

Given a List of words, return the words that can be typed using letters of**alphabet**on only one row's of American keyboard like the image below.

![American keyboard](https://leetcode.com/static/images/problemset/keyboard.png)

**Example 1:**

```text
Input:
 ["Hello", "Alaska", "Dad", "Peace"]

Output:
 ["Alaska", "Dad"]
```

**Note:**

1. You may use one character in the keyboard more than once.
2. You may assume the input string will only contain letters of alphabet.

## 题目链接

[https://leetcode.com/problems/keyboard-row/description/](https://leetcode.com/problems/keyboard-row/description/)

## Python

题目是，判断单词数组里面，每个单词是否由美式键盘上一行字母组成，对于这种字符串处理很容易想到的就是用正则处理，分组匹配，忽略一下大小写

```python
class Solution(object):
    def findWords(self, words):
        """
        :type words: List[str]
        :rtype: List[str]
        """
        import re
        return filter(re.compile(r"^(?i)([qwertyuiop]*|[asdfghjkl]*|[zxcvbnm]*)$").match, words)
```

