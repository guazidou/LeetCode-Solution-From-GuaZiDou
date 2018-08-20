# Longest Substring Without Repeating Characters

## 问题描述

Given a string, find the length of the**longest substring**without repeating characters.

**Examples:**

Given`"abcabcbb"`, the answer is`"abc"`, which the length is 3.

Given`"bbbbb"`, the answer is`"b"`, with the length of 1.

Given`"pwwkew"`, the answer is`"wke"`, with the length of 3. Note that the answer must be a**substring**,`"pwke"`is asubsequenceand not a substring.

## 题目链接

[https://leetcode.com/problems/longest-substring-without-repeating-characters/description/](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)

## Java

比较简单的方法是利用map的不可重复性，暴力遍历算出最长的不可重复串的长度。

```java
public class Solution {
    public int lengthOfLongestSubstring(String s) {
       int maxLength = 0;
        if (s.length() == 0 || s.length() == 1) return s.length();
        for (int i = 0; i < s.length(); i++) {
            Map<Character, Integer> visit = new HashMap<>();
            visit.put(s.charAt(i), 1);
            for (int j = i + 1; j < s.length(); j++) {
                if (visit.containsKey(s.charAt(j))) {
                    if (j - i > maxLength) {
                        maxLength = j - i;
                    }
                    break;
                } else if (j - i + 1 > maxLength) {
                    maxLength = j - i + 1;
                }
                visit.put(s.charAt(j), 1);
            }
        }
        return maxLength;
    }
}
```

