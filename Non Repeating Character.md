## 01. Non Repeating Character

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/non-repeating-character-1587115620/1)

### Problem Description

**Task:** Given a string s consisting of lowercase English Letters. return the first non-repeating character in s. If there is no non-repeating character, return '$'.Examples:Input: s = "geeksforgeeks"

#### Examples

##### Example 1

- **Output:**
```text
'f'
```
- **Explanation:** In the given string, 'f' is the first character in the string which does not repeat.Input: s = "racecar"Output: 'e'Explanation: In the given string, 'e' is the only character in the string which does not repeat.Input: s = "aabbccc"Output: '$'Explanation: All the characters in the given string are repeating.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-11-04 23:45:51
- **Status:** Correct
- **Marks:** 2

```python
from collections import Counter

class Solution:
    def nonRepeatingChar(self, s: str) -> str:
        
        freq = Counter(s)

       
        for char in s:
            if freq[char] == 1:
                return char

       
        return '$'
```

*Generated on: 04/11/2026, 23:46:21*