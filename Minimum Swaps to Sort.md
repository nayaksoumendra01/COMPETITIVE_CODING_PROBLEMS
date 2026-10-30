## 01. Minimum Swaps to Sort

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/minimum-swaps/1)

### Problem Description

**Task:** Given an array arr[] of distinct elements. Find the minimum number of swaps required to sort the array in strictly increasing order.

#### Examples

##### Example 1

- **Input:**
```text
arr[] = [2, 8, 5, 4]
```
- **Output:**
```text
1
```
- **Explanation:** Swap 8 with 4 to get the sorted array.

##### Example 2

- **Input:**
```text
arr[] = [10, 19, 6, 3, 5]
```
- **Output:**
```text
2
```
- **Explanation:** Swap 10 with 3 and 19 with 5 to get the sorted array.

##### Example 3

- **Input:**
```text
arr[] = [1, 3, 4, 5, 6]
```
- **Output:**
```text
0
```
- **Explanation:** Input array is already sorted.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n log n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-31 00:43:43
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def minSwaps(self, arr):
        n = len(arr)
       
        arr_pos = sorted(enumerate(arr), key=lambda x: x[1])

        visited = [False] * n
        ans = 0

        for i in range(n):
           
            if visited[i] or arr_pos[i][0] == i:
                continue
            cycle_size = 0
            j = i
            while not visited[j]:
                visited[j] = True
              
                j = arr_pos[j][0]
                cycle_size += 1

           
            if cycle_size > 1:
                ans += (cycle_size - 1)

        return ans
```

*Generated on: 31/10/2026, 00:44:37*