## 01. Merge Without Extra Space

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/merge-two-sorted-arrays-1587115620/1)

### Problem Description

**Task:** Given two sorted arrays a[] and b[] of size n and m respectively, the task is to merge them in sorted order without using any extra space. Modify a[] so that it contains the first n elements and modify b[] so that it contains the last m elements.Examples:Input: a[] = [2, 4, 7, 10], b[] = [2, 3]

#### Examples

##### Example 1

- **Output:**
```text
a[] = [1, 2, 3, 5, 8, 9], b[] = [10, 13, 15, 20]
```
- **Explanation:** After merging two sorted arrays we get [1, 2, 3, 5, 8, 9, 10, 13, 15, 20].

##### Example 2

- **Input:**
```text
a[] = [0, 1], b[] = [2, 3]
```
- **Output:**
```text
a[] = [0, 1], b[] = [2, 3]
```
- **Explanation:** After merging two sorted arrays we get [0, 1, 2, 3].

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(nlogn + mlogm)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-24 19:20:09
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def mergeArrays(self, a, b):
        n = len(a)
        m = len(b)

        gap = (n + m + 1) // 2

        while gap > 0:
            i = 0
            j = gap

            while j < (n + m):
               
                if j < n:
                    if a[i] > a[j]:
                        a[i], a[j] = a[j], a[i]

              
                elif i < n and j >= n:
                    if a[i] > b[j - n]:
                        a[i], b[j - n] = b[j - n], a[i]

               
                else:
                    if b[i - n] > b[j - n]:
                        b[i - n], b[j - n] = b[j - n], b[i - n]

                i += 1
                j += 1

            if gap == 1:
                break

            
            gap = (gap + 1) // 2
```

*Generated on: 24/10/2026, 19:20:36*