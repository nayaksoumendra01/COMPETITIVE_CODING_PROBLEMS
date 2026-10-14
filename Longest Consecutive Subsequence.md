## 01. Longest Consecutive Subsequence

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/longest-consecutive-subsequence2449/1)

### Problem Description

**Task:** Given an array arr[] of non-negative integers. Find length of the longest sub-sequence such that elements in the subsequence are consecutive integers, the consecutive numbers can be in any order.Examples:Input: arr[] = [2, 6, 1, 9, 4, 5, 3]

#### Examples

##### Example 1

- **Output:**
```text
7
```
- **Explanation:** The longest consecutive subsequence is 9, 10, 11, 12, 13, 14, 15, which has a length of 7.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-14 22:42:33
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def longestConsecutive(self, arr):
        if not arr:
            return 0
            
        num_set = set(arr)
        longest_streak = 0
        
        for num in num_set:
            if (num - 1) not in num_set:
                current_num = num
                current_streak = 1
                
                while (current_num + 1) in num_set:
                    current_num += 1
                    current_streak += 1
                    
                longest_streak = max(longest_streak, current_streak)
                
        Info_streak = longest_streak
        return longest_streak
```

*Generated on: 14/10/2026, 22:43:07*