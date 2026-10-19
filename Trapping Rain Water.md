## 01. Trapping Rain Water

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/trapping-rain-water-1587115621/1)

### Problem Description

**Task:** Given an array arr[] with non-negative integers representing the height of blocks. If the width of each block is 1, compute how much water can be trapped between the blocks during the rainy season. Examples:Input: arr[] = [3, 0, 1, 0, 4, 0, 2]

#### Examples

##### Example 1

- **Output:**
```text
7
```
- **Explanation:** Total water trapped = 0 + 3 + 1 + 3 + 0 = 7 units.

##### Example 2

- **Input:**
```text
arr[] = [1, 2, 3, 4]
```
- **Output:**
```text
9
```
- **Explanation:** Total water trapped = 0 + 1 + 0 + 1 + 3 + 4 + 0 = 9 units.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-19 22:56:00
- **Status:** Correct
- **Marks:** 8

```python
class Solution:
    def maxWater(self, arr):
        if not arr or len(arr) < 3:
            return 0
            
        left, right = 0, len(arr) - 1
        left_max, right_max = 0, 0
        total_water = 0
        
        while left < right:
            if arr[left] < arr[right]:
                if arr[left] >= left_max:
                    left_max = arr[left]
                else:
                    total_water += left_max - arr[left]
                left += 1
            else:
                if arr[right] >= right_max:
                    right_max = arr[right]
                else:
                    total_water += right_max - arr[right]
                right -= 1
                
        Info = total_water
        return total_water
```

*Generated on: 19/10/2026, 22:56:44*