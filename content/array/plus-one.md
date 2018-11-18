# Plus One

## 问题描述

Given a non-negative integer represented as a **non-empty** array of digits, plus one to the integer.

You may assume the integer do not contain any leading zero, except the number 0 itself.

The digits are stored such that the most significant digit is at the head of the list.

### 题目链接

[https://leetcode.com/problems/plus-one/description/](https://leetcode.com/problems/plus-one/description/)

## Python

Python支持大数加法，直接转换到int型，然后进行字符串处理就好

```python
class Solution:
    # @param {integer[]} digits
    # @return {integer[]}
    def plusOne(self, digits):
        return [int(x) for x in str(int(''.join("%s" % y for y in digits)) + 1)]
```

## Java

最容易想到的就是从数组的最后一位加1，往前进位，若最后还有进位说明需要扩容数组第一位置为1，后面数组数据拷贝之前计算的结果。

```java
public class Solution {
    public int[] plusOne(int[] digits) {
        int flag = 1;//进位标志
        for (int i = digits.length - 1; i >= 0; i--) {
            if (digits[i] + flag >= 10) {
                digits[i] = (digits[i] + flag) % 10;
                flag = 1;
            } else {
                digits[i] = (digits[i] + flag) % 10;
                flag = 0;
            }
        }

        if (flag == 1) {
            int[] results = new int[digits.length + 1];
            results[0] = 1;
            for (int i = 0; i < digits.length; i++) {
                results[i + 1] = digits[i];
            }
            return results;
        } else {
            return digits;
        }
    }
}
```

## Go
思路上和Java一样，每位加1，如果有进位就新建一个数组，然后第一位是进位的值，后面copy，没有则直接copy

```go
func plusOne(digits []int) []int {
	c := 1
	for i := len(digits) - 1; i >= 0; i-- {
		sum := digits[i] + c
		digits[i] = sum % 10
		c = sum / 10
	}
	if c > 0 {
		res := make([]int, len(digits)+1)
		res[0] = c
		copy(res[1:], digits)
		return res
	} else {
		return digits
	}
}
```
