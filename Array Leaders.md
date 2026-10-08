## 01. Array Leaders

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/leaders-in-an-array-1587115620/1)

### Problem Description

**Task:** You are given an array arr of positive integers. Your task is to find all the leaders in the array. An element is considered a leader if it is greater than or equal to all elements to its right. The rightmost element is always a leader.Examples:Input: arr = [16, 17, 4, 3, 5, 2]

#### Examples

##### Example 1

- **Output:**
```text
[17, 5, 2]
```
- **Explanation:** Note that there is nothing greater on the right side of 17, 5 and, 2.

##### Example 2

- **Input:**
```text
arr = [10, 4, 2, 4, 1]
```
- **Output:**
```text
[10, 4, 4, 1]Explanation: Note that both of the 4s are in output, as to be a leader an equal element is also allowed on the right. sideInput: arr = [5, 10, 20, 40]Output: [40]Explanation: When an array is sorted in increasing order, only the rightmost element is leader.Input: arr = [30, 10, 10, 5]Output: [30, 10, 10, 5]Explanation: When an array is sorted in non-increasing order, all elements are leaders.
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-08 20:34:58
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def leaders(self, arr):
        n = len(arr)
        if n == 0:
            return []

        leaders_list = [arr[-1]]
        max_so_far = arr[-1]

        for i in range(n - 2, -1, -1):
            if arr[i] >= max_so_far:
                leaders_list.append(arr[i])
                max_so_far = arr[i]

        return leaders_list[::-1]
```

*Generated on: 08/10/2026, 20:35:30*