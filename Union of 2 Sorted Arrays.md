## 01. Union of 2 Sorted Arrays

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/union-of-two-sorted-arrays-1587115621/1)

### Problem Description

**Task:** Given two sorted arrays a[] and b[], where each array may contain duplicate elements , the task is to return the elements in the union of the two arrays in sorted order. Union of two arrays can be defined as the set containing distinct elements that are present in either of the arrays.Examples:Input: a[] = [1, 2, 3, 4, 5], b[] = [1, 2, 3, 6, 7]Output: [1, 2, 3, 4, 5, 6, 7]Explanation: Distinct elements including both the arrays are: 1 2 3 4 5 6 7.Input: a[] = [2, 2, 3, 4, 5], b[] = [1, 1, 2, 3, 4]

#### Examples

##### Example 1

- **Output:**
```text
[1, 2]
```
- **Explanation:** Distinct elements including both the arrays are: 1 2.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n + m)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-10 21:14:51
- **Status:** Correct
- **Marks:** 4

```python
class Solution:    
    def findUnion(self, a, b):
        n, m = len(a), len(b)
        i, j = 0, 0
        union = []

        while i < n and j < m:
        
            if i > 0 and a[i] == a[i - 1]:
                i += 1
                continue
            
            if j > 0 and b[j] == b[j - 1]:
                j += 1
                continue

            if a[i] < b[j]:
                union.append(a[i])
                i += 1
            elif b[j] < a[i]:
                union.append(b[j])
                j += 1
            else:
                union.append(a[i])
                i += 1
                j += 1

        while i < n:
            if i == 0 or a[i] != a[i - 1]:
                union.append(a[i])
            i += 1

        while j < m:
            if j == 0 or b[j] != b[j - 1]:
                union.append(b[j])
            j += 1

        return union
```

*Generated on: 10/10/2026, 21:15:27*