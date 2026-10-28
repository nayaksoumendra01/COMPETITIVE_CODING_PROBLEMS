## 01. Search in a Row-Column Sorted

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/search-in-a-matrix17201720/1)

### Problem Description

**Task:** Given a 2D integer matrix mat[][], where every row and column is sorted in increasing order and a number x, return true if the element x is present in the matrix. Otherwise, return false.Examples:Input: mat[][] = [[3, 30, 38], [20, 52, 54], [35, 60, 69]], x = 62

#### Examples

##### Example 1

- **Output:**
```text
true
```
- **Explanation:** 3 is present in the matrix.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n + m)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-28 17:58:52
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def matSearch(self, mat, x):
        if not mat or not mat[0]:
            return False

        n = len(mat)
        m = len(mat[0])

        row = 0
        col = m - 1

        while row < n and col >= 0:
            current = mat[row][col]

            if current == x:
                return True
            elif current > x:
                col -= 1  
            else:
                row += 1 

        return False
```

*Generated on: 28/10/2026, 17:59:41*