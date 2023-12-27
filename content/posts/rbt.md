---
title : 'Red Black Tree Removal'
date : 2023-12-27T15:49:01-06:00
draft : fasle
author: Hu
tags : ["UW-Madiosn", "CS400", "Red Black Tree"]
categories: ["Courses"]
---

### Red Black Tree

**Red Black Tree Removal**  
Case1: If removing a red node with no black child node , then we can remove this red node directly.  
Case2: If removing a black node with red child node, then change the color of that red child node.  
(Note: The above two cases are only for the removing node with one child node.)  
Case3: If removing a black node with two child nodes, replace with the in-order successor node and change color before removing the black node.  
Case4: Removing a balck node but with no replacing node, then we have to come up with the double black. Check the color of double black's uncle, if uncle is balck and its child node is black as well, then move the double null up higher the tree and change the color of uncle. In the mean time, the color of the root (parent) should be balck.  
![Red Black Tree Removal Case4](/img/case4.png)  
Case5: (Still can not solve the violating issue when we push the double null higher up the tree) when uncle is black, the child node of uncle is red, then we need to do rotation. Rotate the black uncle node towards root, color swap the uncle and root node, then recoloring the uncle's red child node.  
![Red Black Tree Removal Case5](/img/case5.png)  
Case6: When uncle is red, rotate uncle towards root and color swap.  
![Red Black Tree Removal Case6](/img/case6.png)  
Case7(Case5): Uncle is black, uncle only has one red child, turn this case into case5 and resolve the problem.  
![Red Black Tree Removal Case7](/img/case7.png)
