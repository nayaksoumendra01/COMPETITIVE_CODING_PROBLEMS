## 01. Container With Most Water

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/container-with-most-water0535/1)

### Problem Description

**Task:** Given an array arr[] of non-negative integers, where each element arr[i] represents the height of the vertical lines, find the maximum amount of water that can be contained between any two lines, together with the x-axis.Note: In the case of a single vertical line it will not be able to hold water.Examples:Input: arr[] = [1, 5, 4, 3]

#### Examples

##### Example 1

- **Output:**
```text
12
```
- **Explanation:** 5 and 3 are 4 distance apart. So the size of the base is 4. Height of container = min(5, 3) = 3. So, total area to hold water = 4 * 3 = 12.Input: arr[] = [2, 1, 8, 6, 4, 6, 5, 5]Output: 25 Explanation: 8 and 5 are 5 distance apart. So the size of the base is 5. Height of container = min(8, 5) = 5. So, the total area to hold water = 5 * 5 = 25.Constraints:1 ≤ arr.size() ≤ 10⁵⁰ ≤ arr[i] ≤ 10⁴

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-20 22:00:37
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def maxWater(self, arr):
        left = 0
        right = len(arr) - 1
        max_area = 0

        while left < right:
            width = right - left
        
            height = min(arr[left], arr[right])
        
            current_area = width * height
            max_area = max(max_area, current_area)

        
            if arr[left] < arr[right]:
                left += 1
            else:
                right -= 1

        return max_area
```

*Generated on: 20/10/2026, 22:01:09*