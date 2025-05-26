# EX 6C TRAVELLING SALES MAN PROBLEM
## DATE:
## AIM:
To Solve Travelling Sales man Problem for the following graph.

![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)



## Algorithm
1. Define a graph with distances between V cities and select a starting city s.
2. Generate all permutations of the other cities excluding s.
3. For each permutation, calculate total route cost from s through the permutation and back to s.
4. Track and update the minimum route cost found.
5. Return the minimum cost as the shortest route covering all cities once.
6. Note: This brute-force method is feasible only for small V due to factorial complexity. 

## Program:
```
To implement the program for TSP.
Developed by: Vinush CV 
Register Number: 212222230176
```
```py
from sys import maxsize
from itertools import permutations
V = 4
 

def travellingSalesmanProblem(graph, s):
    vetex=[]
    cur=0
    minpath=maxsize
    for i in range(V):
        if i!=s:
            vetex.append(i)
    # k=s
    nextper=permutations(vetex)
    for i in nextper:
        cur=0
        k=s
        for j in i:
            cur+=graph[k][j]
            k=j
        cur+=graph[k][s]
        minpath=min(minpath,cur)
    return minpath
        
   
 
 

if __name__ == "__main__":
 
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],[15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
```

## Output:
![image](https://github.com/user-attachments/assets/cfd30eae-dfbd-4a54-9f32-d586a2f1f7e9)



## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
