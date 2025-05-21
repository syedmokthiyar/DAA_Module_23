# EX 5C Kadane's Algorithm
## DATE:
## AIM:
To write a python program to find the maximum contiguous subarray.


## Algorithm
1. Initialize:

    a.max_so_far = 0 (stores the overall maximum sum)

    b.current_max = 0 (stores the maximum sum ending at the current position)

2. Iterate: Loop through the array elements.

3. Update current_max: For each element, add it to current_max.

4. Update max_so_far and Reset current_max:

   a.If current_max > max_so_far, update max_so_far to current_max.

   b.If current_max < 0, reset current_max to 0.

## Program:
Developed by: GANESH R

Register Number:  212222240029
```python
def maxSubArraySum(a,size):
    max_till_now = a[0]
    max_ending = 0
    for i in range(0, size):
        max_ending = max_ending + a[i]
        if max_ending < 0:
            max_ending = 0
        elif (max_till_now < max_ending):
            max_till_now = max_ending
    return max_till_now
n=int(input())  
a =[] #[-2, -3, 4, -1, -2, 1, 5, -3]
for i in range(n):
    a.append(int(input()))
print("Maximum contiguous sum is", maxSubArraySum(a,n))
```

## Output:
![image](https://github.com/user-attachments/assets/9100c465-2221-49e6-82e3-44d85d36afbb)



## Result:
Thus the program was executed successfully for finding the maximum contiguous sum of subarray..
