## Problem Introduction
You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.


## Explanation
```
    Input: prices = [7,1,5,3,6,4]
    Output: 5
    Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
    Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
```

## Code
```
    def maxProfit(self, prices: List[int]) -> int:
        maxprofit = 0
        minprice = float(inf)

        for price in prices:
            # update minprice before the day
            minprice = min(price, minprice) 
            # update the max profit before the day
            maxprofit = max(maxprofit, price - minprice)

        return maxprofit
```

## Summary

Use Dynamic Programming to solve problems in which we need to reuse the output of subproblem

## Feedback:
If you have any suggestions, I would like to hear from you:<br/>
**Email**: jinxin.hou1994@gmail.com<br/>
**LinkedIn**: http://www.linkedin.com/in/jinxin-hou-a2708898
