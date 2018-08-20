# Pascal's Triangle II

## 问题描述

Given an indexk, return thekthrow of the Pascal's triangle.

For example, givenk= 3,  
Return`[1,3,3,1]`.

**Note:**  
Could you optimize your algorithm to use only O\(k\) extra space?

### 题目链接

[https://leetcode.com/problems/pascals-triangle-ii/description/](https://leetcode.com/problems/pascals-triangle-ii/description/)

## Python

O\(k\)的空间还是挺有意思的

```python
class Solution:
    # @param {integer} rowIndex
    # @return {integer[]}
    def getRow(self, rowIndex):
        row = [1]
        for x in xrange(rowIndex):
            newRow = []
            for y in xrange(len(row)+1):
                if y == 0 or y == len(row):
                    newRow.append(1)
                else:
                    newRow.append(row[y]+row[y-1])
            row = newRow
        return row
```

