## Problem Introduction
Given n non-negative integers a1, a2, ..., an , where each represents a point at coordinate (i, ai). <br/>
n vertical lines are drawn such that the two endpoints of the line i is at (i, ai) and (i, 0).<br/> 
Find two lines, which, together with the x-axis forms a container, such that the container contains the most water.


## Explanation
![image](https://user-images.githubusercontent.com/60673352/115611124-b4be0900-a2b7-11eb-93d9-f9b70a35b78d.png)
```
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
```

## Code
```
def maxArea(self, height: List[int]) -> int:
    i, j = 0, len(height) - 1  # left and right bound of container
    maxVol = 0  # variable to remember max volume

    while(j > i):
        # move the lower bound to find bigger container
        # since lower bound is constraint of container        
        if height[i] < height[j]:
            maxVol = max(maxVol, (j - i) * height[i])  
            i += 1  
        elif height[i] > height[j]: 
            maxVol = max(maxVol, (j - i) * height[j])
            j -= 1
        # when both bounds are equal, move them at the same time
        # since both bounds are the constraint
        else:
            maxVol = max(maxVol, (j - i) * height[i])
            i += 1
            j -= 1
    return maxVol
```

## Summary
Two pointer is a great tool to address search problems in arrays
Two pointer technique: https://cutt.ly/McyIEy0

## Feedback:
If you have any suggestions, I would like to hear from you:<br/>
**Email**: jinxin.hou1994@gmail.com<br/>
**LinkedIn**: http://www.linkedin.com/in/jinxin-hou-a2708898
