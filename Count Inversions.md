## 01. Count Inversions

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/inversion-of-array-1587115620/1)

### Problem Description

**Task:** Given an array of integers arr[]. You have to find the Inversion Count of the array. Inversion count is the number of pairs of elements (i, j) such that i < j and arr[i] > arr[j].Examples:Input: arr[] = [2, 4, 1, 3, 5]Output: 3

#### Examples

##### Example 1

- **Explanation:** As all the elements of array are same, so there is no inversion count.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n log n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-17 23:29:44
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def inversionCount(self, arr):
        def mergeAndCount(arr, temp_arr, left, right):
            inv_count = 0
            if left < right:
                mid = (left + right) // 2

                inv_count += mergeAndCount(arr, temp_arr, left, mid)
                inv_count += mergeAndCount(arr, temp_arr, mid + 1, right)

                inv_count += merge(arr, temp_arr, left, mid, right)
            return inv_count

        def merge(arr, temp_arr, left, mid, right):
            i = left    
            j = mid + 1
            k = left    
            inv_count = 0

            while i <= mid and j <= right:
                if arr[i] <= arr[j]:
                    temp_arr[k] = arr[i]
                    i += 1
                else:

                    temp_arr[k] = arr[j]
                    inv_count += (mid - i + 1)
                    j += 1
                k += 1

            while i <= mid:
                temp_arr[k] = arr[i]
                i += 1
                k += 1

            while j <= right:
                temp_arr[k] = arr[j]
                j += 1
                k += 1

            for i in range(left, right + 1):
                arr[i] = temp_arr[i]

            return inv_count

        temp_arr = [0] * len(arr)
        return mergeAndCount(arr, temp_arr, 0, len(arr) - 1)
```

*Generated on: 17/10/2026, 23:32:47*