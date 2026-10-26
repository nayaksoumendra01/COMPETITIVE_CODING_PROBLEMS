## 01. Minimum Swaps to Group Elements <= K

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/minimum-swaps-required-to-bring-all-elements-less-than-or-equal-to-k-together4847/1)

### Problem Description

**Task:** Given an array arr and a number k. One can apply a swap operation on the array any number of times, i.e choose any two index i and j (i < j) and swap arr[i], arr[j] . Find the minimum number of swaps required to bring all the numbers less than or equal to k together, i.e. make them a contiguous subarray.

#### Examples

##### Example 1

- **Input:**
```text
arr[] = [2, 1, 5, 6, 3], k = 3
```
- **Output:**
```text
1
```
- **Explanation:** To bring elements 2, 1, 3 together, swap index 2 with 4 (0-based indexing), i.e. element arr[2] = 5 with arr[4] = 3 such that final array will be- arr[] = [2, 1, 3, 6, 5]

##### Example 2

- **Input:**
```text
arr[] = [2, 7, 9, 5, 8, 7, 4], k = 6
```
- **Output:**
```text
2
```
- **Explanation:** To bring elements 2, 5, 4 together, swap index 0 with 2 (0-based indexing) and index 4 with 6 (0-based indexing) such that final array will be- arr[] = [9, 7, 2, 5, 4, 7, 8]

##### Example 3

- **Input:**
```text
arr[] = [2, 4, 5, 3, 6, 1, 8], k = 6
```
- **Output:**
```text
0
```

#### Constraints

- **1.** `1 ≤ arr.size() ≤ 10⁶¹ ≤ arr[i] ≤ 10⁶¹ ≤ k ≤ 10⁶`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-26 20:01:17
- **Status:** Correct
- **Marks:** 4

```python
class Solution :
    def minSwap ( self , arr , k ) :
        
        count = 0
        for x in arr:
            if x <= k:
                count += 1

       
        if count <= 1:
            return 0

       
        bad = 0
        for i in range(count):
            if arr[i] > k:
                bad += 1

        ans = bad

       
        n = len(arr)
        left = 0
        right = count

        while right < n:
           
            if arr[left] > k:
                bad -= 1
            left += 1

           
            if arr[right] > k:
                bad += 1
            right += 1

            ans = min(ans, bad)

        return ans
```

*Generated on: 26/10/2026, 20:01:47*