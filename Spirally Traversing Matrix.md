## 01. Spirally Traversing Matrix

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/spirally-traversing-a-matrix-1587115621/1)

### Problem Description

**Task:** Given a rectangular matrix mat[][] of size n x m, and return a 1D array containing all its elements in spiral order.Examples:Input: mat[][] = [[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12], [13, 14, 15, 16]]

#### Examples

##### Example 1

- **Output:**
```text
[32, 44, 27, 23, 62, 50, 28, 54]
```
- **Explanation:** Applying same technique as shown above, output will be [32, 44, 27, 23, 62, 50, 28, 54].Constraints:1 ≤ n, m ≤10000 ≤ mat[i][j] ≤100

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n * m)
- **Expected Auxiliary Space Complexity:** O(n * m)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-29 21:02:39
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def spirallyTraverse(self, mat):
        if not mat or not mat[0]:
            return []

        n = len(mat)
        m = len(mat[0])

        top, bottom = 0, n - 1
        left, right = 0, m - 1

        result = []

        while top <= bottom and left <= right:
          
            for j in range(left, right + 1):
                result.append(mat[top][j])
            top += 1

            
            for i in range(top, bottom + 1):
                result.append(mat[i][right])
            right -= 1

           
            if top <= bottom:
                for j in range(right, left - 1, -1):
                    result.append(mat[bottom][j])
                bottom -= 1

            if left <= right:
                for i in range(bottom, top - 1, -1):
                    result.append(mat[i][left])
                left += 1

        return result
```

*Generated on: 29/10/2026, 21:03:06*