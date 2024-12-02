Input:
    n = Length of the timber
    price = Array of prices for lengths 1 to n
    c = Transaction cost per cut

Output:
    Maximum profit

Steps:
1. Initialize dp[0] = 0 (No profit for length 0).
2. For each length i from 1 to n:
       a. Set dp[i] = price[i] (No cuts scenario).
       b. For each length j from 1 to i:
              dp[i] = max(dp[i], price[j] + dp[i - j] - c)
3. Return dp[n].
