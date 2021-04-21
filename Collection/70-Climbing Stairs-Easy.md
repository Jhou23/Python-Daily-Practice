## Problem Introduction
You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

## Explanation
```
**Example 1:**

Input: n = 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps


**Example 2:**

Input: n = 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```

## Code
```
    def climbStairs(self, n: int) -> int:
            # "a" records number of ways to n stairs F(n)
            # "b" records number of ways to n+1 stairs F(n+1)
            # F(n) = F(n-1) + F(n-2)
            a = b = 1  # climbing to stair 0 and 1 has only 1 way
            for i in range(n):
                a, b = b, a + b
            return a
```
Time: O(n)
Space: O(1)

## Summary
use dynamic programming reduce time complexity

## Feedback:
If you have any suggestions, I would like to hear from you:<br/>
**Email**: jinxin.hou1994@gmail.com<br/>
**LinkedIn**: http://www.linkedin.com/in/jinxin-hou-a2708898
