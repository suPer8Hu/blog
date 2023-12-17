---
title : 'AVL Trees'
date : 2023-12-17T13:38:20-06:00
draft : false
author : Hu
tags: ["UW-Madiosn", "CS400", "AVL Trees"]
categories: ["Courses"]
---

### **AVL Trees**  

AVL Trees is also known as self balancing tree. Self balancing means doing some operations, the tree tries to keep its height as low as possible.  

In an avl tree the height of the two sub trees differ at most one(defined as balance factor), we also have a formula for this balance factor based on this property:  

`balance factor = height of left subtree - height of right subtree`  
`1>=bf>=-1`  

### **AVL Tree Insertion**  
Inserting into an avl tree is same as the insertion into an ordinary bst. But after inserting an element we have to make sure that the tree is balanced. If the balance factor remains −1, 0, or +1 then no rotations are necessary. However, if the balance factor becomes ±2 then the subtree rooted at this node is unbalanced.  

To rebalancing the tree sometimes we need to do rotation, but how can we find the nodes that involves in the rotation process? For example, in the tree below we are trying to insert number 8:  
![AVL tree insertion](/img/avl.png)  
Starting from the new inserting node, moving way up towards the root node until find the first node that is out of balance and that node is the first node we doing rotation. Then move downwards to the path of the insert node find the rest of two nodes involves in the rotation, then find the relationship and finally determine which rotation to use.


