## Best Time to Buy and Sell Stock
### Description
You have an array for which the ith element is the price of a given stock on day i.

If you were only permitted to complete at most one transaction (i.e., buy one and sell one share of the stock), design an algorithm to find the maximum profit.

Note that you cannot sell a stock before you buy one.

### Example 1:
```
Input: [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
             Not 7-1 = 6, as selling price needs to be larger than buying price.
```


### Solution [own]
```java
class Solution {
    public int maxProfit(int[] prices) {
        if(prices == null || prices.length < 2) return 0;
        if(prices.length == 2) return Math.max(prices[1] > prices[0], 0);
        int min = prices[0], maxProfit = 0;
        for(int i = 1; i < prices.length; i++) {
            maxProfit = Math.max(prices[i] - min, maxProfit);
            min = Math.min(prices[i], min);
        }
        return maxProfit;
    }
}
```

Time Complexity : O(n)

Space Complexity: O(1)

### Solution [own]

```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
    if (prices.length <= 1) return 0;
    let profit = prices[1] - prices[0], min = prices[0];
    
    for (let i = 2; i < prices.length; i++) {
        if (prices[i - 1] < min) min = prices[i - 1];
        if (profit < prices[i] - min) profit = prices[i] - min;
    }
    
    return Math.max(0, profit);
};
```

Time Complexity: O(n)

Space Complexity: O(1)
