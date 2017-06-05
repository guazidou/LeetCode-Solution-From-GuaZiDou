# 问题描述

GivennumRows, generate the firstnumRowsof Pascal's triangle.

For example, givennumRows= 5,  
Return

```
[
     [1],
    [1,1],
   [1,2,1],
  [1,3,3,1],
 [1,4,6,4,1]
]
```

## 题目链接

[https://leetcode.com/problems/pascals-triangle/\#/description](https://leetcode.com/problems/pascals-triangle/#/description)

---

# Python

## 思路

模拟一下

## 代码

```py
class Solution(object):
    def generate(self, numRows):
        """
        :type numRows: int
        :rtype: List[List[int]]
        """
        res = list()
        for x in xrange(numRows):
            temp = list()
            for y in xrange(x + 1):
                if y is 0 or y is x:
                    temp.append(1)
                else:
                    temp.append(res[x-1][y-1] + res[x-1][y])
            res.append(temp)
        return res
```

# Java

```java
public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> results = new ArrayList();
        for (int i = 0; i < numRows; i++) {
            Integer[] temp = new Integer[i + 1];
            temp[0] = temp[i] = 1;
            for (int j = 0; j < i - 1; j++) {
                List<Integer> pre = results.get(i - 1);
                temp[j + 1] = pre.get(j) + pre.get(j + 1);
            }
            results.add(Arrays.asList(temp));
        }
        return results;
    }
```



