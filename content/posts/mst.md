---
title : 'Minimum Spanning Tree'
date : 2023-12-18T17:56:52-06:00
draft : false
author: Hu
tags : ["UW-Madiosn", "CS400", "minimum spanning tree", "Kruskal", "Prim"]
categories: ["Courses"]
---

### Minimum Spanning Tree  
A minimum spanning tree (MST) or minimum weight spanning tree is a subset of the edges of a connected, edge-weighted undirected graph that connects all the vertices together, `without any cycles` and with the minimum possible total edge weight. That is, it is a spanning tree whose `sum of edge weights is as small as possible`.  

### Kruskal's Algorithm  
Kruskal’s algorithm to find the minimum cost spanning tree uses the greedy approach. The Greedy Choice is to pick the smallest weight edge that does not cause a cycle in the MST constructed.  

![kruscal Algorithm](/img/kruscal.png)  
To find out the minimum sum of the weight without generating a loop, first list all the weight in a sorted order in a table:  
| Weight | Source | Destination |
|:---  |:---: |:---:  |
|1|7|6|
|2|8|2|
|2|6|5|
|4|0|1|
|4|2|5|
|6|8|6|
|7|2|3|
|7|7|8|
|8|0|7|
|8|1|2|
|9|3|4|
|10|5|4|
|11|1|7|
|14|3|5|  

Then pick all edges one by one from the sorted list(from the smallest weight), emit any if it makes a loop  
The final graph is like:  
![Final MST](/img/mst_kruscal.png)  


### Prim's Algorithm  
Prim’s algorithm is also a Greedy algorithm. This algorithm always starts with a single node and moves through several adjacent nodes, in order to explore all of the connected edges along the way.  
![Prim's Algorithm](/img/prim.png)  
1. First, start with any node, here pick vertex 0.   
2. All the edges connecting the incomplete MST and other vertices are the edges {0, 1} and {0, 7}. Between these two the edge with minimum weight is {0, 1}. So include the edge and vertex 1 in the MST.  
3. The edges connecting the incomplete MST to other vertices are {0, 7}, {1, 7} and {1, 2}. Among these edges the minimum weight is 8 which is of the edges {0, 7} and {1, 2}. Let us here include the edge {0, 7} and the vertex 7 in the MST. [We could have also included edge {1, 2} and vertex 2 in the MST].  
4. The edges that connect the incomplete MST with the fringe vertices are {1, 2}, {7, 6} and {7, 8}. Add the edge {7, 6} and the vertex 6 in the MST as it has the least weight (i.e., 1). {1, 7} can not be connected since it can generate a loop.  
5. Repeat the same logic and get the final MST with this prim's algorithm.  

![Final structure of MST](/img/final1.png)  
The final structure of the MST is as follows and the weight of the edges of the MST is `(4 + 8 + 1 + 2 + 4 + 2 + 7 + 9) = 37`.  
If we had selected the edge {1, 2} in the third step then the MST would look like the following:  

![Final structure of MST](/img/final2.png)  
They have the same weight but different path.