# LeetCode 111 - Minimum Depth of Binary Tree

## Problem

Given the root of a binary tree, find the minimum depth of the tree.

The minimum depth is the number of nodes along the shortest path from the root node to the nearest leaf node.

A leaf node is a node that has no left or right child.

## Example 1

### Input

```text
root = [3,9,20,null,null,15,7]
```

### Output

```text
2
```

### Explanation

The tree is:

```text
        3
       / \
      9   20
         /  \
        15   7
```

The shortest path from the root to a leaf is:

```text
3 → 9
```

Therefore, the minimum depth is `2`.

## Example 2

### Input

```text
root = [2,null,3,null,4,null,5,null,6]
```

### Output

```text
5
```

## Approach

The solution uses recursion to calculate the minimum depth.

There is an important case to handle: if a node has only one child, we cannot simply take the minimum of the two subtree depths because the missing child is not a leaf.

Therefore:

* If the node has no children, its depth is `1`.
* If it has only a right child, use the right subtree.
* If it has only a left child, use the left subtree.
* If it has both children, take the smaller depth.

Finally, add `1` for the current node.

## Algorithm

1. If the root is `None`, return `0`.
2. If there is no left child, calculate the depth using the right subtree.
3. If there is no right child, calculate the depth using the left subtree.
4. If both children exist, calculate the minimum depth of both subtrees.
5. Add `1` for the current node.
6. Return the result.

## Complexity

* **Time Complexity:** `O(n)`
* **Space Complexity:** `O(h)`

Each node may be visited once, and `h` represents the height of the tree used by the recursion stack.

## LeetCode Details

**Problem Number:** 111
**Problem Name:** Minimum Depth of Binary Tree
**Difficulty:** Easy
**Topics:** Binary Tree, Depth-First Search, Breadth-First Search, Recursion

## Language

Python 3

## File

`solution.py`

## Author

T.Nandhini
