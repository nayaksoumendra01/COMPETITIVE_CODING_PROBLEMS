## 01. Search in Rotated Sorted Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/search-in-a-rotated-array4618/1)

### Problem Description

**Task:** Given an array arr[] of distinct elements, which was initially sorted in ascending order but then rotated at some unknown pivot, the task is to find the index of a target key. If the key is not present in the array, return -1.Examples :Input: arr[] = [5, 6, 7, 8, 9, 10, 1, 2, 3], key = 3

#### Examples

##### Example 1

- **Output:**
```text
1
```
- **Explanation:** 42 is found at index 1.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(log n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-22 20:35:30
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def search(self, arr, key):
        low = 0
        high = len(arr) - 1

        while low <= high:
            mid = (low + high) // 2

            
            if arr[mid] == key:
                return mid

            
            if arr[low] <= arr[mid]:
               
                if arr[low] <= key < arr[mid]:
                    high = mid - 1
                else:
                    low = mid + 1
            
            else:
                
                if arr[mid] < key <= arr[high]:
                    low = mid + 1
                else:
                    high = mid - 1

        return -1
```

*Generated on: 22/10/2026, 20:36:03*