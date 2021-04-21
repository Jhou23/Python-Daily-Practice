### Problem Introduction
Given a linked list, swap every two adjacent nodes and return its head.

### Explanation
```
Example 1:
  Input: head = [1,2,3,4]
  Output: [2,1,4,3]

Example 2:
  Input: head = []
  Output: []

Example 3:
  Input: head = [1]
  Output: [1]
```

### Code
```
    class Solution:
    def swapPairs(self, head: ListNode) -> ListNode: 
        dummyHead = ListNode(0)
        dummyHead.next = head
        temp = dummyHead  # set temp location before the first node
        while temp.next and temp.next.next:  # Swap every two adjacent nodes
            # set pointers for nodes to swap
            leftNode = temp.next  
            rightNode = temp.next.next
            # connect temp node to the right node and swap Left and right Node
            temp.next = rightNode
            rightNode.next = leftNode
            leftNode.next = rightNode.next
            # move the temp pointer to new position
            temp = leftNode
        return dummyHead.next
```
Time: O(n)
Space: O(1)

### Summary
Create a dummy head of a linked list is helpful for iteration
Could also apply recursion on this problem
