## 01. Rotate by 90 degree

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/rotate-by-90-degree-1587115621/1)

### Problem Description

**Task:** Given a square matrix mat[][]. The task is to rotate it by 90 degrees in an anti-clockwise direction without using any extra space. Examples:Input: mat[][] = [[0, 1, 2], [3, 4, 5], [6, 7, 8]]

#### Examples

##### Example 1

- **Output:**
```text
[[2, 4], [1, 3]]
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n^2)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-30 00:56:09
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def rotateMatrix(self, mat: list[list[int]]) -> None:
        n = len(mat)

        for i in range(n):
            for j in range(i + 1, n):
                mat[i][j], mat[j][i] = mat[j][i], mat[i][j]

       
        for j in range(n):
            start, end = 0, n - 1
            while start < end:
                mat[start][j], mat[end][j] = mat[end][j], mat[start][j]
                start += 1
                end -= 1
```

*Generated on: 30/10/2026, 00:56:39*