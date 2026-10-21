## 01. Product Array Puzzle

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/product-array-puzzle4525/1)

### Problem Description

**Task:** Given an array, arr[], construct a product array, res[] where each element in res[i] is the product of all elements in arr[] except arr[i]. Return this resultant array, res[].Note: Each element is res[] lies inside the 32-bit integer range.Examples:Input: arr[] = [10, 3, 5, 6, 2]

#### Examples

##### Example 1

- **Output:**
```text
[180, 600, 360, 300, 900]
```
- **Explanation:** For i = 0, res[i] = 3 * 5 * 6 * 2 is 180. For i = 1, res[i] = 10 * 5 * 6 * 2 is 600. For i = 2, res[i] = 10 * 3 * 6 * 2 is 360. For i = 3, res[i] = 10 * 3 * 5 * 2 is 300. For i = 4, res[i] = 10 * 3 * 5 * 6 is 900.

##### Example 2

- **Input:**
```text
arr[] = [12, 0]
```
- **Output:**
```text
[0, 12]Explanation: For i = 0, res[i] is 0.For i = 1, res[i] is 12.
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-21 21:29:45
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def productExceptSelf(self, arr):
        n = len(arr)
        res = [1] * n

       
        left_prod = 1
        for i in range(n):
            res[i] = left_prod
            left_prod *= arr[i]

       
        right_prod = 1
        for i in range(n - 1, -1, -1):
            res[i] *= right_prod
            right_prod *= arr[i]

        return res
```

*Generated on: 21/10/2026, 21:30:21*