# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.





## Algorithm
1. Initialize a square table dp of size n x n.
2. Set diagonal elements of dp to 1.
3. Iterate through increasing substring lengths, filling dp[i][j] based on character comparison and adjacent dp values.
4. The top-right cell dp[0][n-1] holds the result.  

## Program:

Developed by: GANESH R

Register Number:  212222240029
```python
dp = [[-1 for i in range(1001)]for j in range(1001)]
def lps(s1, s2, n1, n2):
    if (n1 == 0 or n2 == 0):
        return 0
    if (dp[n1][n2] != -1):
        return dp[n1][n2]
    if (s1[n1 - 1] == s2[n2 - 1]):
        dp[n1][n2] = 1 + lps(s1, s2, n1 - 1, n2 - 1)
        return dp[n1][n2]
    else:
        dp[n1][n2] = max(lps(s1, s2, n1 - 1, n2), lps(s1, s2, n1, n2 - 1))
        return dp[n1][n2]
seq = input()
n = len(seq)
s2 = seq
s2 = s2[::-1]
print(f"The length of the LPS is",lps(s2, seq, n, n))

```

## Output:
![image](https://github.com/user-attachments/assets/b99fdcb5-eec6-4a9b-8619-f1df4589401a)



## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
