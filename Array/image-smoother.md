# 题目描述

Given a 2D integer matrix M representing the gray scale of an image, you need to design a smoother to make the gray scale of each cell becomes the average gray scale \(rounding down\) of all the 8 surrounding cells and itself. If a cell has less than 8 surrounding cells, then use as many as you can.

# 题目链接

[https://leetcode.com/problems/image-smoother/description/](https://leetcode.com/problems/image-smoother/description/)

---

# Java

题目要求算出每个点的附近点的平均灰度，设要求的点（i,j）附近点范围\(i-1~i+1,j-1~j+1\)

```java
class Solution {
public int[][] imageSmoother(int[][] M) {
        if (M.length == 0 || M[0].length == 0) {
            return M;
        }
        int[][] results = new int[M.length][M[0].length];
        for (int i = 0; i < M.length; i++) {
            for (int j = 0; j < M[0].length; j++) {
                int num = 0;
                int sum = 0;
                for (int k = i - 1; k <= i + 1; k++) {
                    for (int f = j - 1; f <= j + 1; f++) {
                        if (k >= 0 && f >= 0 && k < M.length && f < M[0].length) {
                            num++;
                            sum += M[k][f];
                        }
                    }
                }
                results[i][j] = sum / num;
            }
        }
        return results;
    }
}
```



