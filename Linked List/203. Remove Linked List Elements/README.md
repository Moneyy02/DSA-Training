# 📌 203. Remove Linked List Elements

## 🧠 Problem Description

Given the `head` of a singly linked list and an integer `val`, remove
all the nodes of the linked list that have `Node.val == val`, and return
the new head of the linked list.

------------------------------------------------------------------------

## 🖼 Example Visualization

### Input

    head = [1,2,6,3,4,5,6]
    val = 6

### Linked List Representation

1 → 2 → 6 → 3 → 4 → 5 → 6\
(Remove all nodes with value 6)

### Output

    [1,2,3,4,5]

------------------------------------------------------------------------

## 📥 Input

-   `head` → The head of a singly linked list\
-   `val` → Integer value to remove

------------------------------------------------------------------------

## 📤 Output

-   Return the head of the modified linked list after removing all nodes
    whose value equals `val`.

------------------------------------------------------------------------

## 📌 Constraints

-   The number of nodes in the list is in the range `[0, 10⁴]`
-   `1 <= Node.val <= 50`
-   `0 <= val <= 50`
