# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:
## AIM:
To find longest common subsequence using Dynamic Programming.



## Algorithm
1. Initialize a 2D DP table dp[m+1][n+1] with zeros.

2. Loop through strings X and Y, comparing characters.

3. If characters match, set dp[i][j] = dp[i-1][j-1] + 1.

4. If not, set dp[i][j] = max(dp[i-1][j], dp[i][j-1]).

5. Return dp[m][n] as the length of the LCS (optionally reconstruct sequence). 

## Program:

Developed by: GANESH R

Register Number:  212222240029

```python
def lcs(u, v):
    """Return c where c[i][j] contains length of LCS of u[i:] and v[j:]."""
    c = [[-1]*(len(v) + 1) for _ in range(len(u) + 1)]
    for i in range(len(u) + 1):
        c[i][len(v)] = 0
    for j in range(len(v)):
        c[len(u)][j] = 0
 
    for i in range(len(u) - 1, -1, -1):
        for j in range(len(v) - 1, -1, -1):
            if u[i] == v[j]:
                c[i][j] = 1 + c[i + 1][j + 1]
            else:
                c[i][j] = max(c[i + 1][j], c[i][j + 1])
    return c
 
def print_lcs(u, v, c):
    """Print one LCS of u and v using table c."""
    i = j = 0
    while not (i == len(u) or j == len(v)):
        if u[i] == v[j]:
            print(u[i], end='')
            i += 1
            j += 1
        elif c[i][j + 1] > c[i + 1][j]:
            j += 1
        else:
            i += 1
 
u = input()
v = input()
c = lcs(u, v)
print_lcs(u, v, c)

```

## Output:
![image](https://github.com/user-attachments/assets/508bbd87-6284-4507-952d-b462ffa67598)



## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
