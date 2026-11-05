## 01. Longest Substring with Distinct Characters

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/longest-distinct-characters-in-string5848/1)

### Problem Description

**Task:** Given a string s, find the length of the longest substring with all distinct characters.

#### Examples

##### Example 1

- **Input:**
```text
s = "geeksforgeeks"
```
- **Output:**
```text
7
```
- **Explanation:** "eksforg" is the longest substring with all distinct characters.

##### Example 2

- **Input:**
```text
s = "aaa"
```
- **Output:**
```text
1
```
- **Explanation:** "a" is the longest substring with all distinct characters.

##### Example 3

- **Input:**
```text
s = "abcdefabcbb"
```
- **Output:**
```text
6
```
- **Explanation:** The longest substring with all distinct characters is "abcdef", which has a length of 6.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-11-05 23:19:55
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def longestUniqueSubstr(self, s: str) -> int:
        last_index = [-1] * 256
        max_len = 0
        start = 0

        for end in range(len(s)):
            curr_char = ord(s[end])
            if last_index[curr_char] >= start:
                start = last_index[curr_char] + 1
            last_index[curr_char] = end
            max_len = max(max_len, end - start + 1)

        return max_len
```

*Generated on: 05/11/2026, 23:20:23*