# 237. Delete Node in a Linked List

## Problem Statement

There is a singly-linked list, and you are given a node to delete. You will not be given access to the head of the list.

Delete the given node such that:

- The value of the given node no longer exists in the list.
- The number of nodes decreases by one.
- The order of nodes before and after the deleted node remains unchanged.

## Example

Input:
Linked List = [4,5,1,9]
Node = 5

Output:
[4,1,9]

Explanation:
The node with value 5 is deleted from the linked list.

## Approach

Since we do not have access to the head or the previous node, we cannot remove the given node directly.

Instead:

1. Copy the value of the next node into the current node.
2. Update the next pointer to skip the next node.

This effectively removes the next node while making the current node appear deleted.

## Algorithm

1. Assign `node->val = node->next->val`.
2. Assign `node->next = node->next->next`.
3. Return.

## C++ Solution

```cpp
class Solution {
public:
    void deleteNode(ListNode* node) {
        node->val = node->next->val;
        node->next = node->next->next;
    }
};

