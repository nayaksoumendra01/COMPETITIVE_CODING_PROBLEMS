## 01. Intersection of Two Sorted Arrays

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/intersection-of-two-sorted-array-1587115620/1)

### Problem Description

**Task:** Given two sorted arrays arr1[] and arr2[]. Your task is to return the intersection of both arrays.Intersection of two arrays is said to be elements that are common in both arrays. The intersection should not count duplicate elements.Note: If there is no intersection then return an empty array.

#### Examples

##### Example 1

- **Input:**
```text
arr1[] = [1, 2, 3, 4], arr2[] = [2, 4, 6, 7, 8]
```
- **Output:**
```text
[2, 4]
```
- **Explanation:** 2 and 4 are only common elements in both the arrays.

##### Example 2

- **Input:**
```text
arr1[] = [1, 2, 2, 3, 4], arr2[] = [2, 2, 4, 6, 7, 8]
```
- **Output:**
```text
[2, 4]
```
- **Explanation:** 2 and 4 are the only common elements.

##### Example 3

- **Input:**
```text
arr1[] = [1, 2], arr2[] = [3, 4]
```
- **Output:**
```text
[]
```
- **Explanation:** No common elements.

#### Constraints

- **1.** `1 ≤ arr1.size(),arr2.size() ≤ 10⁵¹ ≤ arr1[i], arr2[i] ≤ 10⁶`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n + m)
- **Expected Auxiliary Space Complexity:** O(min(n, m))

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-11 19:47:25
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def intersection(self, arr1, arr2):
        i, j = 0, 0
        n, m = len(arr1), len(arr2)
        res = []

        while i < n and j < m:
            
            if i > 0 and arr1[i] == arr1[i - 1]:
                i += 1
                continue

            
            if j > 0 and arr2[j] == arr2[j - 1]:
                j += 1
                continue

            if arr1[i] < arr2[j]:
                i += 1
            elif arr1[i] > arr2[j]:
                j += 1
            else:
                res.append(arr1[i])
                i += 1
                j += 1

        return res
```

*Generated on: 11/10/2026, 19:48:01*