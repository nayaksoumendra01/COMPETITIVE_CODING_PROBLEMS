## 01. Zero Sum Subarray

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/subarray-with-0-sum-1587115621/1)

### Problem Description

**Task:** Given an array of integers, arr[]. Find if there is a subarray (of size at least one) with 0 sum. Return true/false depending upon whether there is a subarray present with 0-sum or not. Examples:Input: arr[] = [4, 2, -3, 1, 6]

#### Examples

##### Example 1

- **Output:**
```text
false
```
- **Explanation:** 0 is one of the elements in the array so there exist a subarray with sum 0.Input: arr = [1, 2, -1]

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** Not found
- **Expected Auxiliary Space Complexity:** Not found

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-15 21:08:01
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def subArrayExists(self, arr):
        seen_sums = set()
        prefix_sum = 0

        for num in arr:
            prefix_sum += num
            if prefix_sum == 0 or prefix_sum in seen_sums or num == 0:
                return True

            seen_sums.add(prefix_sum)

        return False
```

*Generated on: 15/10/2026, 21:26:30*