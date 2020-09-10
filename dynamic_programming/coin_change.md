322. Coin Change




You are given coins of different denominations and a total amount of money amount. Write a function to compute the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

Example 1:

Input: coins = [1, 2, 5], amount = 11
Output: 3 

Explanation: 11 = 5 + 5 + 1
Example 2:

Input: coins = [2], amount = 3
Output: -1


```
class Solution:
    def coinChange(self, coins: List[int], amount: int) -> int:
        dp = [-1]*(amount+1)
        dp[0] = 0
        answer = MinCoins(amount,coins,dp)
        if answer == float('inf'):
            return -1
        else:
            return answer
        
def MinCoins(amt,coins,dp):
    if amt == 0:
        return 0
    
    ans = float('inf')
    
    for i in range(0,len(coins)):
        if amt-coins[i] >= 0:
            subAns = 0
            if dp[amt-coins[i]] != -1:
                subAns = dp[amt-coins[i]]
            else:
                subAns = MinCoins(amt-coins[i],coins,dp)
            
            if subAns + 1 < ans:
                ans = subAns + 1
                
    dp[amt] = ans
                
    return dp[amt]
        
        
```        
