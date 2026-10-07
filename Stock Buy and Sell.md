## 01. Stock Buy and Sell

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/stock-buy-and-sell-1587115621/1)

### Problem Description

**Task:** Given an array arr[] denoting the cost of stock on each day, the task is to find the maximum total profit if we can buy and sell the stocks any number of times.Note: We can only sell a stock which we have bought earlier and only one instance of stock can be traded.Examples:Input: arr[] = [100, 180, 260, 310, 40, 535, 695]

#### Examples

##### Example 1

- **Output:**
```text
0
```
- **Explanation:** Don't Buy the stock.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-07 20:48:53
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    
    def maxProfit(self, arr):
        profit = 0
        
        for i in range(1, len(arr)):
            
            if arr[i] > arr[i - 1]:
                profit += arr[i] - arr[i - 1]
                
        return profit
```

*Generated on: 07/10/2026, 20:49:33*