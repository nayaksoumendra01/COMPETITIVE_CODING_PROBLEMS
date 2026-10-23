## 01. Peak in Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/peak-element/1)

### Problem Description

**Task:** Given an array arr[] where no two adjacent elements are same, find the index of a peak element. An element is considered to be a peak if it is greater than its adjacent elements (if they exist). If there are multiple peak elements, Return index of any one of them. The output will be "true" if the index returned by your function is correct; otherwise, it will be "false".Note: Consider the element before the first element and the element after the last element to be negative infinity.Examples :Input: arr = [1, 2, 4, 5, 7, 8, 3]

#### Examples

##### Example 1

- **Output:**
```text
true
```
- **Explanation:** Element 20 at index 1 is a peak since 10 < 20 > 15. Index 5 (value 90) is also a peak, but returning any one peak index is valid.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(log n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-23 13:37:15
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def peakElement(self, arr):
        n = len(arr)
        low = 0
        high = n - 1

        while low <= high:
            mid = (low + high) // 2

            
            if (mid == 0 or arr[mid] > arr[mid - 1]) and (mid == n - 1 or arr[mid] > arr[mid + 1]):
                return mid

            
            elif mid < n - 1 and arr[mid] < arr[mid + 1]:
                low = mid + 1

            
            else:
                high = mid - 1

        return -1
```

*Generated on: 23/10/2026, 13:37:42*