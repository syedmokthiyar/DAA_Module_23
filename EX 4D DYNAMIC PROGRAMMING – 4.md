# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.





## Algorithm
1. Base Cases: If either string is empty, the cost is the length of the other.
2. Last Chars Match: If the last characters are the same, no operation needed; recurse on prefixes.
3. Last Chars Differ: Consider insert, delete, substitute (cost 1 each), and take the minimum of the recursive calls on the resulting substrings.
4. Return Minimum: The final result is the minimum number of operations found through the recursive calls.

## Program:

Developed by: GANESH R

Register Number:  212222240029

```python
def LD(s, t):
    #########  Add your code here ###########
    if s == "":
        return len(t)
    if t == "":
        return len(s)
    if s[-1] == t[-1]:
        cost = 0
    else:
        cost = 1
    res = min([LD(s[:-1], t)+1, LD(s, t[:-1])+1, LD(s[:-1], t[:-1]) + cost])
    return res
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))


```

## Output:
![image](https://github.com/user-attachments/assets/815c6319-10bd-40d6-aec7-7a49259c7669)



## Result:
Thus the program was executed successfully for finding edit distance between two strings.
