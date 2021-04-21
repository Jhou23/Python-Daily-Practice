## Problem Introduction
Given head, the head of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

## Explanation
![image](https://user-images.githubusercontent.com/60673352/115609631-c9010680-a2b5-11eb-8dad-3d9745aec69a.png)
```
Input: head = [3,2,0,-4], pos = 1
Output: true
Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).
```

## Code
![image](https://user-images.githubusercontent.com/60673352/115609963-34e36f00-a2b6-11eb-8c21-70a815b23f0a.png)

```
    def hasCycle(self, head: ListNode) -> bool:
        if not head or not head.next: # when linked list is void or has 1 value
        return False
        # set slow and fast pointer
        slow = head
        fast = head.next
        # if the linked list is a cycle, two pointer will meet, then it's a cycle
        while slow != fast:
            if not fast or not fast.next:
                return False
            slow = slow.next
            fast = fast.next.next
        return True
```
    Time: O(n)
    Space: O(1)

## Summary
  two pointers method can reduce time and space complexity

## Feedback:
If you have any suggestions, I would like to hear from you:<br/>
**Email**: jinxin.hou1994@gmail.com<br/>
**LinkedIn**: http://www.linkedin.com/in/jinxin-hou-a2708898
