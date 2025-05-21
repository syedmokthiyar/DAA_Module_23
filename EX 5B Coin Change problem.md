# EX 5B Coin Change Problem
## DATE:
## AIM:
To compute the fewest number of coins that we need to make up the amount given.


## Algorithm
1. Initialize a table to store the minimum number of coins for each amount (0 to target).

2. Iterate through each amount and each coin denomination.

3. Calculate the minimum coins needed for the current amount using the current coin.

4. The last entry in the table gives the final result.  

## Program:
Developed by: GANESH R

Register Number:  212222240029

```python
class Solution(object):
   def coinChange(self, coins, amount):
        dp = [float('inf')] * (amount + 1)  # Initialize a DP array with infinity values
        dp[0] = 0  

        for coin in coins:
            for i in range(coin, amount + 1):
                dp[i] = min(dp[i], dp[i - coin] + 1)  # Update the DP array

        return dp[amount] if dp[amount] != float('inf') else -1
      
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))


print(ob1.coinChange(s,amt))

```

## Output:
![image](https://github.com/user-attachments/assets/a140b74e-de54-4b66-9fc5-85d3f8ec219b)



## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
