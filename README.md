# Leetcode-122.-Best-Time-to-Buy-and-Sell-Stock-II
# Description
You are given an integer array prices where prices[i] is the price of a given stock on the ith day.

On each day, you may decide to buy and/or sell the stock. You can only hold at most one share of the stock at any time. However, you can buy it then immediately sell it on the same day.

Find and return the maximum profit you can achieve.
# Solution
The goal is to maximize profit by making as many profitable transactions as possible.

Unlike LeetCode 121 (where you can only make one buy-sell transaction), here you can buy and sell multiple times, but never hold more than one stock at a time.

If we observe the stock price graph, the maximum profit is simply the sum of all upward movements in price.

Every time the price goes up from prices[i] to prices[i+1], we can imagine buying at i and selling at i+1.

This works because buying and selling on the same day is allowed, and there’s no transaction fee in the problem.

Example 1:

Input: prices = [7,1,5,3,6,4]

Output: 7

Explanation: Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 5-1 = 4.


Then buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 6-3 = 3.

Total profit is 4 + 3 = 7.

Example 2:

Input: prices = [1,2,3,4,5]\

Output: 4

Explanation: Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.

Total profit is 4.

Example 3:

Input: prices = [7,6,4,3,1]

Output: 0

Explanation: There is no way to make a positive profit, so we never buy the stock to achieve the maximum profit of 0.
# Algorithm
1. Initialize profit = 0.
2. Loop through prices from day 0 to day n-2.
3. If prices[i+1] > prices[i], add the difference (prices[i+1] - prices[i]) to profit.
4. Return profit.
# Code
class Solution:

    def maxProfit(self, prices: List[int]) -> int:
        
        profit=0
        for i in range(1,len(prices)):
            if prices[i]>prices[i-1]:
                summ+=prices[i]-prices[i-1]
            
            
        return profit
# Complexity
Time Complexity:
O(n) — We only iterate through the price list once, updating the minimum price and maximum profit along the way.

Space Complexity: 
O(1) — Only a few variables are used (minPrice, maxProfit), regardless of the input size.
