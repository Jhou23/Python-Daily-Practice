# Python Problems Collection

This repository is the log of my daily **Python** practice. I hope it can be of some help for you.


## Introduction

Each problem typically has four parts: 
1. Goal of Query
2. Table Introduction
3. Solution
4. Summary

I would recommend you read the problem first, understand the tables and relationship between tables, and think about solutions first.
My solution is a reference, and Summary is about my thoughts.

Happy Practicing!


## Feedback

If you have any suggestions to the collections such as the format of sharing and better solution, I am happy to speak with you.

**Email**   : jinxin.hou1994@gmail.com
**LinkedIn**: http://www.linkedin.com/in/jinxin-hou-a2708898



## Example

### Problem Introduction
Given an integer array nums, return all the triplets [nums[i], nums[j], nums[k]] such that i != j, i != k, and j != k, and nums[i] + nums[j] + nums[k] == 0.

Notice that the solution set must not contain duplicate triplets.

### Explanation
```
**Example 1:**

Input: nums = [-1,0,1,2,-1,-4]
Output: [[-1,-1,2],[-1,0,1]]


**Example 2:**

Input: nums = []
Output: []


**Example 3:**

Input: nums = [0]
Output: []
```

### Code
```
def threeSum(self, nums: List[int]) -> List[List[int]]:
    # get rid of list with less than 3 values
    n = len(nums)
    res = []
    if (not nums or n < 3):  
        return res
    nums.sort()  # prepare for two pointers method
    for i in range(n):
        if (nums[i] > 0):  # if the minimum is positive, no solution
            return res
        if (i > 0 and nums[i] == nums[i-1]):  # avoid duplicate results
            continue
        L = i + 1  # left pointer
        R = n - 1  # right pointer
        while (L < R):
            s = nums[i] + nums[L] + nums[R]  
            if (s == 0):
                res.append([nums[i], nums[L], nums[R]])
                while (R > L and nums[R] == nums[R-1]):  # avoid duplicate results
                    R -= 1
                while (R > L and nums[L] == nums[L+1]):
                    L += 1
                R -= 1
                L += 1
            elif (s < 0):
                L += 1
            else:
                R -= 1
    return res
```
![image](https://user-images.githubusercontent.com/60673352/115610580-0d40d680-a2b7-11eb-95ab-a91be8d2bd5f.png)
![image](https://user-images.githubusercontent.com/60673352/115610586-10d45d80-a2b7-11eb-963a-c2933a8a555a.png)

Time: O(n^2) - brute force O(n^3)
Space: O(1)

### Summary
method:
1 sort the array in ascending order.
2 fix an index i
3 set left pointer L as i + 1 and right pointer R as len(array) - 1
4 sum up: s = array[i] + array[L] + array[R]
5 if s < 0 move left pointer to the right to improve s
if s > 0 move right pointer to the left to decrease s
if s == 0, remember the results (and avoid duplicate solutions)
