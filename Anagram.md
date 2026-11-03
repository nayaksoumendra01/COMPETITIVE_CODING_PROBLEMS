## 01. Anagram

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/anagram-1587115620/1)

### Problem Description

**Task:** Given two non-empty strings s1 and s2, consisting only of lowercase English letters, determine whether they are anagrams of each other or not. Two strings are considered anagrams if they contain the same characters with exactly the same frequencies, regardless of their order.Examples:Input: s1 = "geeks" s2 = "kseeg"Output: true Explanation: Both the string have same characters with same frequency. So, they are anagrams.Input: s1 = "allergy", s2 = "allergyy" Output: false Explanation: Although the characters are mostly the same, s2 contains an extra 'y' character. Since the frequency of characters differs, the strings are not anagrams. Input: s1 = "listen", s2 = "lists" Output: false Explanation: The characters in the two strings are not the same — some are missing or extra. So, they are not anagrams.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n + m)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-11-03 21:14:12
- **Status:** Correct
- **Marks:** 2

```python
from collections import Counter

class Solution:
    def areAnagrams(self, s1: str, s2: str) -> bool:
      
        if len(s1) != len(s2):
            return False

        return Counter(s1) == Counter(s2)
```

*Generated on: 03/11/2026, 21:14:41*