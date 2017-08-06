# 问题描述

In English, we have a concept called`root`, which can be followed by some other words to form another longer word - let's call this word`successor`. For example, the root`an`, followed by`other`, which can form another word`another`.

Now, given a dictionary consisting of many roots and a sentence. You need to replace all the`successor`in the sentence with the`root`forming it. If a`successor`has many`roots`can form it, replace it with the root with the shortest length.

You need to output the sentence after the replacement.

## 题目链接

https://leetcode.com/problems/replace-words/description/

---

# Java

题目要求用最短的单词匹配前缀，故可以先按单词长度排序，然后依次比较匹配替换。

```java
public class Solution {
     public String replaceWords(List<String> dict, String sentence) {
        dict.sort(Comparator.comparingInt(String::length));
        String[] words = sentence.split(" ");
        StringBuilder sb = new StringBuilder();
        for (String word : words) {
            for (String d : dict) {
                if (word.startsWith(d)) {
                    word = d;
                    break;
                }
            }
            sb.append(word + " ");
        }
        return sb.toString().trim();
    }
}
```



