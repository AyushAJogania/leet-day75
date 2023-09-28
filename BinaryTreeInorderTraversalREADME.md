# leet-day75

# Inorder Traversal of Binary Tree

This C++ solution demonstrates how to perform an inorder traversal of a binary tree using a recursive approach.

## Problem Statement

Given the root of a binary tree, you need to return the inorder traversal of its nodes' values.

An inorder traversal of a binary tree is a depth-first traversal, which starts from the left subtree, then visits the current node, and finally explores the right subtree.

## Solution Approach

### Function Explanation

1. `void solve(TreeNode * root, vector<int> & ans)`: A recursive helper function that performs the inorder traversal.
   - `root`: A pointer to the current node being visited.
   - `ans`: A reference to a vector that stores the inorder traversal result.

2. `vector<int> inorderTraversal(TreeNode* root)`: The main function that initiates the traversal.
   - `root`: The root of the binary tree.
   - Returns a vector containing the inorder traversal of the binary tree.

### How It Works

The `solve` function is a recursive function that follows the inorder traversal logic:

1. If the current `root` node is `NULL`, the function returns, as there's nothing to traverse.

2. If the `root` node is not `NULL`, the function recursively calls itself on the left subtree (`root->left`).

3. After exploring the left subtree, the value of the current `root` node is pushed into the `ans` vector.

4. Finally, the function recursively calls itself on the right subtree (`root->right`).

The `inorderTraversal` function serves as the entry point. It initializes an empty vector (`ans`) to store the traversal result and then calls the `solve` function with the root node and the `ans` vector.

## Example


    1
   / \
  2   3
 / \
4   5


Calling `inorderTraversal(root)` would return `[4, 2, 5, 1, 3]`, which is the inorder traversal of the tree.

## Usage

You can use this solution to obtain the inorder traversal of any binary tree by calling the `inorderTraversal` function with the root of the tree.

```cpp
TreeNode* root = ...; // Initialize your binary tree
Solution solution;
vector<int> result = solution.inorderTraversal(root);
```

## Complexity Analysis

The time complexity of this solution is O(n), where n is the number of nodes in the binary tree, as we visit each node once.

The space complexity is also O(n) due to the space required for the recursion stack and the `ans` vector.
