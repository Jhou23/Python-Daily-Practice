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
    https://media-exp1.licdn.com/dms/image/C5622AQE47I1HYClvTA/feedshare-shrink_1280/0/1617813545186?e=1622073600&v=beta&t=l2T2XV4oZfWIUM9zr20H96WzDtt4I-hevVvn5mLfHBA
    Create a dummy head of a linked list is helpful for iteration
    Could also apply recursion on this problem
