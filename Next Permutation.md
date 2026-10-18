## 01. Next Permutation

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/next-permutation5226/1)

### Problem Description

**Task:** Given an array of integers arr[] representing a permutation, implement the next permutation that rearranges the numbers into the lexicographically smallest greater (or next) permutation.
If no next permutation exists, rearrange the numbers into the lowest possible order (i.e., sorted in ascending order).

#### Examples

##### Example 1

- **Input:**
```text
arr[] = [2, 4, 1, 7, 5, 0]
```
- **Output:**
```text
[2, 4, 5, 0, 1, 7]
```
- **Explanation:** The next permutation of the given array is [2, 4, 5, 0, 1, 7].

##### Example 2

- **Input:**
```text
arr[] = [3, 2, 1]
```
- **Output:**
```text
[1, 2, 3]
```
- **Explanation:** As arr[] is the last permutation, the next permutation is the lowest one.

##### Example 3

- **Input:**
```text
arr[] = [3, 4, 2, 5, 1]
```
- **Output:**
```text
[3, 4, 5, 1, 2]
```
- **Explanation:** The next permutation of the given array is [3, 4, 5, 1, 2].

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-18 22:29:34
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def nextPermutation(self, arr):
        n = len(arr)
       
        i = n - 2
        while i >= 0 and arr[i] >= arr[i + 1]:
            i -= 1

       
        if i >= 0:
           
            j = n - 1
            while arr[j] <= arr[i]:
                j -= 1
           
            arr[i], arr[j] = arr[j], arr[i]

       
        left, right = i + 1, n - 1
        while left < right:
            arr[left], arr[right] = arr[right], arr[left]
            left += 1
            right -= 1

        return arr
```

*Generated on: 18/10/2026, 22:30:05*