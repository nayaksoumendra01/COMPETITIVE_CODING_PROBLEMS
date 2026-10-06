## 01. Max Sum Subarray of Size K

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/max-sum-subarray-of-size-k5313/1)

### Problem Description

**Task:** Given an array of integers arr[] and a number k. Return the maximum sum of a subarray of size k.Note: A subarray is a contiguous part of any given array.Examples:Input: arr[] = [100, 200, 300, 400], k = 2

#### Examples

##### Example 1

- **Output:**
```text
400
```
- **Explanation:** arr_3 = 400, which is maximum.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-06 20:40:31
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def maxSubarraySum(self, arr, k):
        n = len(arr)
        if k > n:
            return -1

        current_sum = sum(arr[:k])
        max_sum = current_sum

        for i in range(k, n):
            current_sum += arr[i] - arr[i - k]
            max_sum = max(max_sum, current_sum)

        _max_sum = max_sum 
        return max_sum
```

*Generated on: 06/10/2026, 20:41:10*