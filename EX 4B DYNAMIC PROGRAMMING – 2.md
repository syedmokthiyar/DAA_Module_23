# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..



## Algorithm
1. Compare characters of both strings.
2. Build a table tracking matching substring lengths.
3. Find the maximum length in the table.
4. Extract the substring(s) corresponding to the maximum length.
## Program:
Developed by: GANESH R

Register Number:  212222240029

```python
def LCS(X, Y, m, n):
    maxLength = 0
    endingIndex = m
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]

X = input()
Y = input()
m = len(X)
n = len(Y)
print('The longest common substring is', LCS(X, Y, m, n))

```

## Output:

![image](https://github.com/user-attachments/assets/26b392b1-5161-44ed-9a03-d20aeca2dd16)


## Result:
Thus the program was executed successfully for finding the longest common substring .
