Consider, [7, 1, 5, 3, 6, 4]

Each element in the array denotes the stock price on that day.

The objective is to find the maximum profit that one can get buy buying at one day and selling at one day. Only one transaction is allowed

The approach to this would be to find a maximum difference subarray (max difference meaning buy at a day which has less price, and sell at a day that gives max returns)

So basically it can be solved like this
1) First we need to find the best Buying day
2) This can be done by iterating through the array and stopping at the first minimum element we get
3) In this case, while iterating, we encounter 7 first, then 1 comes
4) So lets assume 1 is the best day to buy. So we buy stock at 1 price
5) Next, we keep seeing that for this day, what is the max profit obtained
6) So we iterate, i.e. we come across 5, we calculate profit i.e. 5-1 = 4
7) Then, we store this profit in variable 
8) Next, we iterate again. We encounter 3 this time. Note that our buy day has not changed as it is the most minimum we have encountered till now ( as 5 >1, and 3 is also > 1)
9) So, calculate profit i.e. 3-1 = 2
10) Is this current obtained profit greater than our profit stored previously in the profit variable? is 2 greater than 4? no. So 4 is still the nicest profit we can get.
11) We arrive at 6. We calculate and profit is 5. This is better than 4 we got at step 6.
12) So 5 is max profit till now 
13) Then we iterate to 4, 4-1 is 3 which is not greater than profit of 5.

Hence our max profit or the max difference sub array is 5 ([1,5,3,6])

Code :
```
    def maxProfit(self, prices: List[int]) -> int:
        minimum_price_till_now = float('inf')
        profit = 0
        max_profit = 0
        
        
        for price in prices:
            if price < minimum_price_till_now:
                minimum_price_till_now = price
            
                
            profit = price - minimum_price_till_now
            max_profit = max(max_profit, profit)
            
        return max_profit

```


