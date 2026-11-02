## 01. Palindrome String

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/palindrome-string0817/1)

### Problem Description

**Task:** Given a string s, find if it is a palindrome. A string is considered a palindrome if it reads the same forwards and backwards.

#### Examples

##### Example 1

- **Input:**
```text
s = "abba"
```
- **Output:**
```text
true
```
- **Explanation:** "abba" reads the same forwards and backwards, so it is a palindrome.

##### Example 2

- **Input:**
```text
s = "abc"
```
- **Output:**
```text
false
```
- **Explanation:** "abc" does not read the same forwards and backwards, so it is not a palindrome.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-11-02 18:39:40
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
       
        return s == s[::-1]
```

*Generated on: 02/11/2026, 18:40:08*