## 01. can someone explain why is it accepted???? in the comment section almost everyone is using (maxValue+1) but range of int value is exceeding in this....

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/-rearrange-array-alternately-1587115620/1)

### Problem Description

**Task:** Given an array of non-negative integers. Your task is to rearrange the array elements alternatively i.e. first element should be the max value, the second should be the min value, the third should be the second max, the fourth should be the second min, and so on.

> **Note:** Modify the original array itself. You do not have to return anything.

#### Examples

##### Example 1

- **Input:**
```text
arr[] = [1, 2, 3, 4, 5, 6]
```
- **Output:**
```text
[6, 1, 5, 2, 4, 3]
```
- **Explanation:** Max element = 6, min = 1, second max = 5, second min = 2, and so on... The modified array is: [6, 1, 5, 2, 4, 3]

##### Example 2

- **Input:**
```text
arr[] = [10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110]
```
- **Output:**
```text
[110, 10, 100, 20, 90, 30, 80, 40, 70, 50, 60]
```
- **Explanation:** Max element = 110, min = 10, second max = 100, second min = 20, and so on... Modified array is : [110, 10, 100, 20, 90, 30, 80, 40, 70, 50, 60]

##### Example 3

- **Input:**
```text
arr[] = [1]
```
- **Output:**
```text
[1]
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n log n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-13 21:01:56
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def rearrange(self, arr):
        arr.sort()
        n = len(arr)
        result = []

        left = 0
        right = n - 1

        while left <= right:
            result.append(arr[right])
            right -= 1

            if left <= right:
                result.append(arr[left])
                left += 1

        for i in range(n):
            arr[i] = result[i]
```

*Generated on: 13/10/2026, 21:02:27*