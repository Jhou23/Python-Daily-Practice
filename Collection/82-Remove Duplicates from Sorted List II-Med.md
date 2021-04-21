## Problem Introduction
Given the head of a sorted linked list, delete all nodes that have duplicate numbers, leaving only distinct numbers from the original list. Return the linked list sorted as well.


## Explanation
![image](https://user-images.githubusercontent.com/60673352/115614904-3dd73f00-a2bc-11eb-9716-746956af98ca.png)
```
Input: head = [1,2,3,3,4,4,5]
Output: [1,2,5]
```

## Code
```
    def deleteDuplicates(self, head: ListNode) -> ListNode:
        if not head:return head
        if head.next and head.val == head.next.val:
            while head.next != None and head.val == head.next.val:
                head = head.next
            return self.deleteDuplicates(head.next)
        else:
            head.next = self.deleteDuplicates(head.next)
        return head
```

## Summary
Use recursion to solve problems that can be broken down into smaller, repetitive problems.

## Feedback:
If you have any suggestions, I would like to hear from you:<br/>
**Email**: jinxin.hou1994@gmail.com<br/>
**LinkedIn**: http://www.linkedin.com/in/jinxin-hou-a2708898
