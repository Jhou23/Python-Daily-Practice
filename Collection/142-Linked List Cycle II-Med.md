# 142. Linked List Cycle II

## Problem Introduction
Given a linked list, return the node where the cycle begins. 

## Explanation
```
![image](https://user-images.githubusercontent.com/60673352/116464689-48548400-a83a-11eb-81d4-0c87d3c9b8a4.png)
Input: head = [3,2,0,-4], pos = 1
Output: tail connects to node index 1
Explanation: There is a cycle in the linked list, where tail connects to the second node.
```

## Code
```
def detectCycle(self, head: ListNode) -> ListNode:
    fast, slow = head, head
    while True:
        if not (fast and fast.next): 
            return
        fast, slow = fast.next.next, slow.next
        if fast == slow: break
    fast = head
    while fast != slow:
        fast, slow = fast.next, slow.next
    return fast
```
Time: O(N)
Space: O(1)

## Summary
![image](https://user-images.githubusercontent.com/60673352/116465214-ed6f5c80-a83a-11eb-8328-2af460a5ddec.png)
```
two pointer method
1. set a fast(move 2 steps per operation) and a slow(move 1 step per operation) pointer. If there is a cycle, two pointers will meet.
2. when the fast and slow pointer meet, distance(fast) = 2 * distance(slow)
3. Set the distance from the head to the door of the circle as A
       the distance from the start point of cycle to the meeting point of two pointer as B
       the distance from the meeting point to the start point as C
4. Then distance(slow) = A + B; distance(fast) = A + B + C + B; Since D(fast) = 2*D(slow), so A = C
5. Because the distance from head to start point is A, which equals to the distance(C) from meeting point to start point,
   we set fast pointer to the head and step as 1 per/ operation. Then the fast and slow pointer will meet each other at the start point.
```

## Feedback:
If you have any suggestions, I would like to hear from you:<br/>
**Email**: jinxin.hou1994@gmail.com<br/>
**LinkedIn**: http://www.linkedin.com/in/jinxin-hou-a2708898
