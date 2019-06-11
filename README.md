# DP-easy
# [1] Minimum number of jumps
# Given an array of integers where each element represents the max number of steps that can be made forward from that element. Write a function to return the minimum number of jumps to reach the end of the array (starting from the first element). If an element is 0, then cannot move through that element.
# Example:        Input: arr[] = {1, 3, 5, 8, 9, 2, 6, 7, 6, 8, 9}          Output: 3 (1-> 3 -> 8 ->9)

1.solution 0(n^2)
test=int(input())
while(test>0):
    test-=1
    n=int(input())
    arr=[int(x) for x in input().split()]
    jumps = [0 for i in range(n)] 
    for i in range(n-2, -1, -1): 
        if (arr[i] == 0): 
            jumps[i] = float('inf') 
        elif (arr[i] >= n - i - 1): 
            jumps[i] = 1
        else:
            min = float('inf')
            for j in range(i + 1, n): 
                if (j <= arr[i] + i): 
                    if (min > jumps[j]): 
                        min = jumps[j] 
            if (min != float('inf')): 
                jumps[i] = min + 1
            else: 
                jumps[i] = min
    if jumps[0]!=float('inf'):
        print(jumps[0])
    else:
        print("-1")
  2.solution - 0(n)
