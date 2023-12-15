---
title : 'BST Review'
date : 2023-12-14T01:04:40-06:00
draft : False
tags: ["UW-Madiosn", "CS400", "BST"]
categories: ["Courses"]
---

  
### **The properties of the binary search tree**  
1. All elements in the left subtree is less that the root node.    
2. All elements in the right subtree is greater than the root node.  
3. All the elements in the tree is unique.

### **BST Search**  
To search one node just compare it with the cur root node, if it less than the root node then go left subtree and otherwise to find it through the right subtree.  
**Time complexity: O(H) where H is the height of the bst**  

### **BST Traversal**  
- In order(also known as sorted order):left subtree, root, right
- Pre-order:root, left, right
- Post-order:left, right, root 
- Level-order:from top level to bottom  

Example: 
![Traversal](/img/bst.png)
In this example, if we use in-order traversal, it will be `10,20,30,40,50,55,60,65,70`.  
In pre-order, it will be `50,30,10,20,40,70,60,55,65`.  
In post-order, it will be `20,10,40,30,55,65,60,70,50`.  
Level-order, it will be `50,30,70,10,40,60,20,55,65`.

### **The height of the tree**
The height of the tree is the number of nodes from root node to the tree's deepest leaf
Relation between height(H) and number of nodes(N) in the tree: `N = (2^H) - 1`

### **BST Insertion**
Start with search and find the null node for the correct spot of the new inserting node
**Time complexity: O(H) where H is the height of the bst**  

### **BST Deletion**
Deletion has three cases, check the children of this deletion node:
1. No children(leaf), delete directly
2. Single childre (Make sure that single child stays attach to the tree after deletion)
3. Two child (There are two options for deletion of the node with two child - replace the root node with in order predecessor or replace the root node with in order successor)  

Notes: 
- predecessor: right most element in the left subtree
- successor: left most elemnent in the right subtree

**Calculation for time complexity:**  
`N=(2^H)-1`  
`log2(N+1)=H` equivalent to `O(logN)`