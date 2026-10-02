## 01. Missing in Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/missing-number-in-array1416/1)

### Problem Description

**Task:** You are given an array arr[] of size n - 1 that contains distinct integers in the range from 1 to n (inclusive). This array represents a permutation of the integers from 1 to n with one element missing. Your task is to identify and return the missing element.Examples:Input: arr[] = [1, 2, 3, 5]

#### Examples

##### Example 1

- **Output:**
```text
2
```
- **Explanation:** Only 1 is present so the missing element is 2.Constraints:1 ≤ arr.size() ≤ 10⁶¹ ≤ arr[i] ≤ arr.size() + 1

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (2)

#### Solution 1 (Python)

- **Submitted:** 2026-10-03 01:03:21
- **Status:** Correct
- **Marks:** 0

```python
class Solution :  
    def missingNum(self, arr):
        n = len(arr) + 1
        Sum = n * (n + 1) // 2
        actual_sum = sum(arr)
        return Sum - actual_sum
```

#### Solution 2 (Python)

- **Submitted:** 2026-09-25 12:23:28
- **Status:** Correct
- **Marks:** 2

```python
class Solution :  
    def missingNum(self, arr):
        n = len(arr) + 1
        total_sum = n * (n + 1) // 2
        actual_sum = sum(arr)
        return total_sum - actual_sum
```

*Generated on: 03/10/2026, 01:04:00*