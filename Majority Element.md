## 01. Majority Element

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/majority-element-1587115620/1)

### Problem Description

**Task:** Given an array arr[]. Find the majority element in the array. If no majority element exists, return -1.Note: A majority element in an array is an element that appears strictly more than arr.size()/2 times in the array.Examples:Input: arr[] = [1, 1, 2, 1, 3, 5, 1]

#### Examples

##### Example 1

- **Output:**
```text
-1
```
- **Explanation:** Since, no element is present more than 2/2 times, so there is no majority element.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-04 00:23:22
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def majorityElement(self, arr):
        n = len(arr)

        count = {}

        for num in arr:
            if num in count:
                count[num] += 1
            else:
                count[num] = 1

            if count[num] > n // 2:
                return num

        return -1
```

*Generated on: 04/10/2026, 00:24:02*