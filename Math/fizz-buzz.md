# 问题描述

Write a program that outputs the string representation of numbers from 1 ton.

But for multiples of three it should output “Fizz” instead of the number and for the multiples of five output “Buzz”. For numbers which are multiples of both three and five output “FizzBuzz”.

**Example:**

```
n = 15,

Return:
[
    "1",
    "2",
    "Fizz",
    "4",
    "Buzz",
    "Fizz",
    "7",
    "8",
    "Fizz",
    "Buzz",
    "11",
    "Fizz",
    "13",
    "14",
    "FizzBuzz"
]

```


## 题目连接

[https://leetcode.com/problems/fizz-buzz/description/](https://leetcode.com/problems/fizz-buzz/description/)

---

# Python {#python}

这道题目本来是没有类别的, 有个除法, 就勉强算了

```python
class Solution(object):
    def fizzBuzz(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        def FizzBuzz(x):
            res = ""
            if x % 3 == 0:
                res += "Fizz"
            if x % 5 == 0:
                res += "Buzz"
            if res == "":
                res = str(x)
            return res
        return map(FizzBuzz, range(1, n+1))
```