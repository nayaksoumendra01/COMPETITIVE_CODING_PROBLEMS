## 01. Rotate Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/rotate-array-by-n-elements-1587115621/1)

### Problem Description

**Task:** Given an array arr[]. Rotate the array to the left (counter-clockwise direction) by d steps, where d is a positive integer. Do the mentioned change in the array in place.Note: Consider the array as circular.Examples :Input: arr[] = [1, 2, 3, 4, 5], d = 2

#### Examples

##### Example 1

- **Output:**
```text
[3, 9, 1, 7]
```
- **Explanation:** when we rotate 9 times, we'll get [3, 9, 1, 7] as resultant array.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-01 13:29:05
- **Status:** Correct
- **Marks:** 1

```python
class Solution:
    def rotateArr(self, arr, d):
        n = len(arr)
        d %= n
        
        def reverse(start, end):
            while start < end:
                arr[start], arr[end] = arr[end], arr[start]
                start, end = start + 1, end - 1

        reverse(0, d - 1)

        reverse(d, n - 1)

        reverse(0, n - 1)
```

*Generated on: 01/10/2026, 13:29:40*