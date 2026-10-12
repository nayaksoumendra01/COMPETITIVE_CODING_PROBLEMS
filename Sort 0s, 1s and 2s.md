## 01. Sort 0s, 1s and 2s

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/sort-an-array-of-0s-1s-and-2s4231/1)

### Problem Description

**Task:** Given an array arr[] containing only 0s, 1s, and 2s. Sort the array in ascending order. Examples:Input: arr[] = [0, 1, 2, 0, 1, 2]

#### Examples

##### Example 1

- **Output:**
```text
[0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 2, 2]
```
- **Explanation:** 0s, 1s and 2s are segregated into ascending order.Follow up: Could you come up with a one-pass algorithm using only constant extra space?

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-12 21:47:46
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def sort012(self, arr):
        low, mid, high = 0, 0, len(arr) - 1

        while mid <= high:
            if arr[mid] == 0:
                arr[low], arr[mid] = arr[mid], arr[low]
                low += 1
                mid += 1
            elif arr[mid] == 1:
                mid += 1
            else: 
                arr[mid], arr[high] = arr[high], arr[mid]
                high -= 1

        return arr
```

*Generated on: 12/10/2026, 21:48:54*