## 01. Count Occurrences in Sorted

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/number-of-occurrence2259/1)

### Problem Description

**Task:** Given a sorted array arr[] and a number target, find the number of occurrences of target in given array. Examples:Input: arr[] = [1, 1, 2, 2, 2, 2, 3], target = 2

#### Examples

##### Example 1

- **Output:**
```text
3
```
- **Explanation:** target = 12 occurs 3 times in the given array so the output is 3.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(log n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-27 15:02:48
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def countFreq(self, arr, target):
        def findFirst(arr, target):
            low, high = 0, len(arr) - 1
            first = -1
            while low <= high:
                mid = (low + high) // 2
                if arr[mid] == target:
                    first = mid
                    high = mid - 1
                elif arr[mid] < target:
                    low = mid + 1
                else:
                    high = mid - 1
            return first

        def findLast(arr, target):
            low, high = 0, len(arr) - 1
            last = -1
            while low <= high:
                mid = (low + high) // 2
                if arr[mid] == target:
                    last = mid
                    low = mid + 1 
                elif arr[mid] < target:
                    low = mid + 1
                else:
                    high = mid - 1
            return last

        first = findFirst(arr, target)
        if first == -1:
            return 0

        last = findLast(arr, target)
        return last - first + 1
```

*Generated on: 27/10/2026, 15:03:18*