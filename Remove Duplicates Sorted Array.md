## 01. Remove Duplicates Sorted Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/remove-duplicate-elements-from-sorted-array/1)

### Problem Description

**Task:** You are given a sorted array arr[] containing positive integers. Your task is to remove all duplicate elements from this array such that each element appears only once. Return an array containing these distinct elements in the same order as they appeared.Examples :Input: arr[] = [2, 2, 2, 2, 2]

#### Examples

##### Example 1

- **Output:**
```text
[2]
```
- **Explanation:** After removing all the duplicates only one instance of 2 will remain i.e. [2] so modified array will contains 2 at first position and you should return array containing [2] after modifying the array.

##### Example 2

- **Input:**
```text
arr[] = [1, 2, 4]
```
- **Output:**
```text
[1, 2, 4]Explanation: As the array does not contain any duplicates so you should return [1, 2, 4].
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-02 01:04:51
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def removeDuplicates(self, arr):
        if len(arr) == 0:
            return []

        j = 1

        for i in range(1, len(arr)):
            if arr[i] != arr[i - 1]:
                arr[j] = arr[i]
                j += 1

        return arr[:j]
```

*Generated on: 02/10/2026, 01:05:31*