# EX 6A CHERRY PICK UP PROBLEM
## DATE:
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm
1. Initialize 3D DP `dp[row][col1][col2]` for max cherries collected by two robots.
2. Set base case: robots start at top row, columns 0 and last.
3. Iterate row-wise, updating DP for all robot position pairs.
4. Calculate cherries picked, avoiding double counting.
5. Update DP using previous row’s valid moves `(col1 ± 1, col2 ± 1)`.
6. Return max cherries when robots reach the last row.

## Program:
```
To implement the program for Cherry pickup problem.
Developed by: Vinush CV
Register Number: 212222230176
```
```py
class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        self.maxx=0
        def cp1(row,col,arr,cc):
            if row<0 or row>=len(arr[0]) or col<0 or col>=len(arr[0]) or arr[row][col]==-1:
                return 
            if row==len(arr)-1 and col==len(arr[0])-1:
                helper(row,col,arr,cc)
                
            cherry=arr[row][col]
            arr[row][col]=0
            cp1(row,col+1,arr,cc+cherry)
            cp1(row+1,col,arr,cc+cherry)
            arr[row][col]=cherry
        def helper(row,col,arr,cc):
            if row<0 or row>=len(arr[0]) or col<0 or col>=len(arr[0]) or arr[row][col]==-1:
                return 
            if row==0 and col==0:
                self.maxx=max(self.maxx,cc)
                return 
            cherry=arr[row][col]
            arr[row][col]=0
            helper(row,col-1,arr,cc+cherry)
            helper(row-1,col,arr,cc+cherry)
            arr[row][col]=cherry
        cp1(0,0,grid,0)
        return self.maxx
        
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid))
```

## Output:
![image](https://github.com/user-attachments/assets/0dfeecd9-016d-4553-98c3-199d6c290535)



## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
