## 01. Maximum Product Subarray

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/maximum-product-subarray3604/1)

### Problem Description

**Task:** Given an array arr[] that contains positive and negative integers (may contain 0 as well). Find the maximum product that we can get in a subarray of arr[].Note: It is guaranteed that the answer fits in a 32-bit integer.ExamplesInput: arr[] = [-2, 6, -3, -10, 0, 2]

#### Examples

##### Example 1

- **Output:**
```text
30
```
- **Explanation:** The subarray with maximum product is [-3, -10] with product = (-3) * (-10) = 30.Input: arr[] = [2, 3, 4] Output: 24 Explanation: For an array with all positive elements, the result is product of all elements.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-25 23:00:17
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def maxProduct(self, arr):
        if not arr:
            return 0

        max_so_far = arr[0]
        min_so_far = arr[0]
        result = arr[0]

        for i in range(1, len(arr)):
            curr = arr[i]

            
            if curr < 0:
                max_so_far, min_so_far = min_so_far, max_so_far

            max_so_far = max(curr, max_so_far * curr)
            min_so_far = min(curr, min_so_far * curr)

            result = max(result, max_so_far)

        return result
```

*Generated on: 25/10/2026, 23:00:45*