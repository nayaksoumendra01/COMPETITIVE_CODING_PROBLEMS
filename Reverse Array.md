## 01. Reverse Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/reverse-an-array/1)

### Problem Description

**Task:** You are given an array of integers arr[]. You have to reverse the given array.

> **Note:** Modify the array in place.

#### Examples

##### Example 1

- **Input:**
```text
arr = [1, 4, 3, 2, 6, 5]
```
- **Output:**
```text
[5, 6, 2, 3, 4, 1]Explanation: The elements of the array are [1, 4, 3, 2, 6, 5]. After reversing the array, the first element goes to the last position, the second element goes to the second last position and so on. Hence, the answer is [5, 6, 2, 3, 4, 1].
```

##### Example 2

- **Input:**
```text
arr = [4, 5, 2]
```
- **Output:**
```text
[2, 5, 4]Explanation: The elements of the array are [4, 5, 2]. The reversed array will be [2, 5, 4].
```

##### Example 3

- **Input:**
```text
arr = [1]
```
- **Output:**
```text
[1]Explanation: The array has only single element, hence the reversed array is same as the original.
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-09-27 12:40:54
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def reverseArray(self, arr):
        left=0
        right = len(arr)-1
        
        while left < right:
            arr[left], arr[right] =arr[right], arr[left]
            left+=1
            right-=1
```

*Generated on: 27/09/2026, 12:41:20*