## 01. Arrange Anagrams Together

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/print-anagrams-together/1)

### Problem Description

**Task:** Given an array arr[] of strings, group all anagrams together. Two strings are anagrams if they contain the same characters with the same frequencies, possibly in a different order.Return a 2D array, where each inner array contains a group of anagrams. The relative order of strings within each group should be the same as their order in arr.Examples:Input: arr[] = ["act", "god", "cat", "dog", "tac"]

#### Examples

##### Example 1

- **Output:**
```text
[["act", "cat", "tac"], ["god", "dog"]]
```
- **Explanation:** There are 2 groups of anagrams "god", "dog" make group 1. "act", "cat", "tac" make group 2.

##### Example 2

- **Input:**
```text
arr[] = ["no", "on", "is"]
```
- **Output:**
```text
[["is"], ["no", "on"]]
```
- **Explanation:** There are 2 groups of anagrams "is" makes group 1. "no", "on" make group 2.Input: arr[] = ["listen", "silent", "enlist", "abc", "cab", "bac", "rat", "tar", "art"]Output: [["abc", "cab", "bac"], ["listen", "silent", "enlist"], ["rat", "tar", "art"]]Explanation: Group 1: "abc", "bac", and "cab" are anagrams. Group 2: "listen", "silent", and "enlist" are anagrams. Group 3: "rat", "tar", and "art" are anagrams

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n*m*logm)
- **Expected Auxiliary Space Complexity:** O(n * m)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-11-06 23:20:04
- **Status:** Correct
- **Marks:** 4

```python
from collections import defaultdict

class Solution:
    def anagrams(self, arr):
       
        anagram_map = defaultdict(list)

        for s in arr:
            key = "".join(sorted(s))
            anagram_map[key].append(s)

       
        return list(anagram_map.values())
```

*Generated on: 06/11/2026, 23:20:32*