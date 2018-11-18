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

```go

func addStrings(num1 string, num2 string) string {
	var s1, s2, ind, c int64
	maxLen := int64(math.Max(float64(len(num1)), float64(len(num2))))
	res := make([]byte, maxLen)
	i := len(num1) - 1
	j := len(num2) - 1
	ind = int64(math.Max(float64(i), float64(j)))

	for i >= 0 || j >= 0 {
		if i >= 0 {
			s1 = int64([]byte(num1)[i] - '0')
		} else {
			s1 = 0
		}
		if j >= 0 {
			s2 = int64([]byte(num2)[j] - '0')
		} else {
			s2 = 0
		}

		sum := s1 + s2 + c
		res[ind] = byte(sum%10) + '0'
		c = sum / 10

		ind--
		i--
		j--
	}

	if c > 0 {
		return strings.Join([]string{strconv.FormatInt(c, 10), string(res)}, "")
	}

	return string(res)
}

```
