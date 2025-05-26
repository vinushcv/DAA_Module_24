# EX 6B KNAPSACK PROBLEM
## DATE:
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.



## Algorithm
1. Initialize 2D DP table `dp[n+1][W+1]`.
2. Iterate through items and capacities.
3. Set `dp[i][w] = 0` if item index or capacity is 0.
4. If item weight ≤ capacity, set `dp[i][w]` to max of including or excluding the item.
5. Otherwise, set `dp[i][w]` to value from previous item at same capacity.
6. Return `dp[n][W]` as the maximum value achievable.
   
## Program:
```
To implement the program for 0/1 knapsack problem.
Developed by: Vinush CV
Register Number: 212222230176
```
```py
def knapSack(W, wt, val, n):
    dp=[[-1]*(W+1) for _ in range(len(val)+1)]
    for i in range(W+1):
        dp[0][i]=0
    for i in range(n+1):
        dp[i][0]=0
    for i in range(1,n+1):
        for j in range(1,W+1):
            if j<wt[i-1]:
                dp[i][j]=dp[i-1][j]
            else:
                dp[i][j]=max(dp[i-1][j],dp[i-1][j-wt[i-1]]+val[i-1])
    return dp[n][W]
x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))
n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```

## Output:
![image](https://github.com/user-attachments/assets/ac2745d0-e7f2-4c9f-a411-1b7c8f242de3)



## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
