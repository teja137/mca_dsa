Function MaxProfit(n, prices, c):
    Declare profit[0 to n] as an array of integers

    profit[0] = 0

    For length from 1 to n:
        max_profit = -infinity  // Start with a very low value for max_profit
        For cut_length from 1 to length:
            current_profit = prices[cut_length] + profit[length - cut_length] - c
            max_profit = max(max_profit, current_profit)
        EndFor
        profit[length] = max_profit
    EndFor

    Return profit[n]
EndFunction
