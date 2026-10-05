## 01. Two Sum - Pair with Given Sum

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/key-pair5616/1)

### Problem Description

**Task:** Given an array arr[] of integers and another integer target. Determine if there exist two distinct indices such that the sum of their elements is equal to the target.Examples:Input: arr[] = [0, -1, 2, -3, 1], target = -2

#### Examples

##### Example 1

- **Output:**
```text
false
```
- **Explanation:** No pair is possible as only one element is present in arr[]

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-05 22:04:34
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def twoSum(self, arr, target):
        seen = set()
        for num in arr:
            complement = target - num
            if complement in seen:
                return True
            seen.add(num)
        return False
```

*Generated on: 05/10/2026, 22:05:08*