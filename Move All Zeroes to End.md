## 01. Move All Zeroes to End

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/move-all-zeroes-to-end-of-array0751/1)

### Problem Description

**Task:** Given an array arr[] of non-negative integers, move all the zeros to the end of the array while maintaining the relative order of the non-zero elements. Perform the operation in place, without using an extra array.Examples:Input: arr[] = [1, 2, 0, 4, 3, 0, 5, 0]

#### Examples

##### Example 1

- **Output:**
```text
[1, 2, 4, 3, 5, 0, 0, 0]
```
- **Explanation:** The three zeros are moved to the end while the order of the non-zero elements remains unchanged.

##### Example 2

- **Input:**
```text
arr[] = [10, 20, 30]
```
- **Output:**
```text
[10, 20, 30]
```
- **Explanation:** No change in array as there are no 0s.

##### Example 3

- **Input:**
```text
arr[] = [0, 0]
```
- **Output:**
```text
[0, 0]
```
- **Explanation:** No change in array as there are all 0s.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-09-30 01:32:29
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def pushZerosToEnd(self, arr):
        index = 0

        for i in range(len(arr)):
            if arr[i] != 0:
                arr[index] = arr[i]
                index += 1

        while index < len(arr):
            arr[index] = 0
            index += 1
```

*Generated on: 30/09/2026, 01:33:04*