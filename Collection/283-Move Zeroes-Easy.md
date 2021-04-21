## Problem Introduction
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

## Explanation
```
Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
```

## Code
```
def moveZeroes(self, nums: List[int]) -> None:
    zero = 0  # pointer for 0 index
    for i in range(len(nums)):  # move non-zeros forward
        if nums[i] != 0:
            nums[zero], nums[i] =  nums[i], nums[zero]
            zero += 1
```

## Summary
Time Complexity: O(n)
Space Complexity: O(1)

index & pointer for inplace array change.

## Feedback:
If you have any suggestions, I would like to hear from you:<br/>
**Email**: jinxin.hou1994@gmail.com<br/>
**LinkedIn**: http://www.linkedin.com/in/jinxin-hou-a2708898
