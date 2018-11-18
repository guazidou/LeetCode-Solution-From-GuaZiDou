# Integer to Roman

## 问题描述

Given an integer, convert it to a roman numeral.

Input is guaranteed to be within the range from 1 to 3999.

## 题目链接

[https://leetcode.com/problems/integer-to-roman/description/](https://leetcode.com/problems/integer-to-roman/description/)

## Java

利用字典来处理

```java
public class Solution {
    public String intToRoman(int num) {

        String[][] c = {
                {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"},
                {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"},
                {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"},
                {"", "M", "MM", "MMM"}
        };

        StringBuilder roman = new StringBuilder();
        roman.append(c[3][num / 1000 % 10]);
        roman.append(c[2][num / 100 % 10]);
        roman.append(c[1][num / 10 % 10]);
        roman.append(c[0][num % 10]);
        return roman.toString();
    }
}
```

```go
import "strings"

func intToRoman(num int) string {
	dict := [][]string{
		{"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"},
		{"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"},
		{"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"},
		{"", "M", "MM", "MMM"},
	}

	res := make([]string, 0, 4)
	res = append(res, dict[3][(num/1000)%10])
	res = append(res, dict[2][(num/100)%10])
	res = append(res, dict[1][(num/10)%10])
	res = append(res, dict[0][num%10])

	return strings.Join(res, "")
}
```
