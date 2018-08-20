# Add Strings

## 题目描述

Given two non-negative integers`num1`and`num2`represented as string, return the sum of`num1`and`num2`.

Note:

The length of both num1 and num2 is &lt; 5100.

Both num1 and num2 contains only digits 0-9.

Both num1 and num2 does not contain any leading zero.

You must not use any built-in BigInteger library or convert the inputs to integer directly.

## 题目链接

[https://leetcode.com/problems/add-strings/description/](https://leetcode.com/problems/add-strings/description/)

## Java

字符串求和

```java
class Solution {
     public String addStrings(String num1, String num2) {
        int maxLength = num1.length() >= num2.length() ? num1.length() : num2.length();
        String result = "";
        int flag = 0;
        for (int i = 0; i < maxLength; i++) {
            if (num1.length() - i - 1 >= 0 && num2.length() - i - 1 >= 0) {
                int s = flag + num1.charAt(num1.length() - i - 1) - '0' + num2.charAt(num2.length() - i - 1) - '0';
                flag = s >= 10 ? 1 : 0;
                result += s % 10;
            } else if (num1.length() - i - 1 < 0) {
                int s = flag + num2.charAt(num2.length() - i - 1) - '0';
                flag = s >= 10 ? 1 : 0;
                result += s % 10;
            } else if (num2.length() - i - 1 < 0) {
                int s = flag + num1.charAt(num1.length() - i - 1) - '0';
                flag = s >= 10 ? 1 : 0;
                result += s % 10;
            }
        }
        if (flag > 0) result += flag;
        return new StringBuilder(result).reverse().toString();
    }
}
```

