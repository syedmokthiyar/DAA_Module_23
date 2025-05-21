# EX 5A Minimum Cost Path
## DATE:
## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.




## Algorithm
1. Base Cases: Reach destination: return cell cost. Go out of bounds: return infinity.

2. Recursive Calls: Explore down, right, and diagonal paths.

3. Calculate Cost: Add current cell cost to the minimum cost of the explored paths.

4. Return: The minimum cost to reach the destination.
## Program:
Developed by: GANESH R

Register Number:  212222240029

```python
R = int(input())
C = int(input())
def minCost(cost, m, n):
    tc = [[0 for x in range(C)] for x in range(R)]
    tc[0][0] = cost[0][0]
    for i in range(1, m+1):
        tc[i][0] = tc[i-1][0] + cost[i][0]
    for j in range(1, n+1):
        tc[0][j] = tc[0][j-1] + cost[0][j]
    for i in range(1, m+1):
        for j in range(1, n+1):
            tc[i][j] = min(tc[i-1][j-1], tc[i-1][j], tc[i][j-1]) + cost[i][j]
 
    return tc[m][n]
 
cost = [[1, 2, 3],
        [4, 8, 2],
        [1, 5, 3]]
print(minCost(cost, R-1, C-1))

```

## Output:
![image](https://github.com/user-attachments/assets/4789c35a-dc8b-4b75-aa37-4e8ac48e7172)



## Result:
Thus the above program was executed successfully for finding the minimum cost.
