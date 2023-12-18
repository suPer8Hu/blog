---
title : 'BTree'
date : 2023-12-17T14:54:37-06:00
draft : false
author : Hu
tags : ["UW-Madiosn", "CS400", "BTree"]
categories: ["Courses"]
---

### **Btree**

The idea we saw earlier of putting multiple set (list, hash table) elements together into large chunks that exploit locality can also be applied to trees. Binary search trees are not good for locality because a given node of the binary tree probably occupies only a fraction of any cache line. `B-trees` are a way to get better locality by putting multiple elements into each tree node.  
  
Degree m: Maximum number of the children   
The actual elements of the collection are stored in the leaves of the tree, and the nonleaf nodes contain only keys. B-tree with a degree of 4 also known as `2-3-4 tree`.  

**Properties of 2-3-4 tree**  
1. Every path from the root to a leaf has the same length(all leaves are at the same depth)  
2. If a node has n child, this node can contain up to `n-1` keys  
3. Every node (except the root) is at least half full  
4. The root has at least two children if it is not a leaf.  

2 nodes: 1 key - 2 children  
3 nodes: 2 key - 3 children  
4 nodes: 3 key - 4 children  

For example, look at the 2-3-4 tree below:  
![2-3-4 tree](/img/btree.png)  
This root of the 2-3-4 tree has 3 children, and for the nonleaf(which is the root node in this case), it contains 2 keys 10 and 20 with 3 child below.  

**2-3-4 Tree Isertion**  
Insert the values into a 2-3-4 trees we use the method called `preemptive split`(push the middle one up)  

Try to insert in this order:`1,2,3,4,5,6,7,8,9,10` use this [visualization](https://www.cs.usfca.edu/~galles/visualization/BTree.html)
