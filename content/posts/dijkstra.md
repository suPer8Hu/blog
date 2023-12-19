---
title : "Dijkstra's Algorithm"
date : 2023-12-18T18:39:55-06:00
draft : false
author: Hu
tags : ["UW-Madiosn", "CS400", "Dijkstra"]
categories: ["Courses"]
---

### Dijkstra's Algorithm  
Given a weighted graph and a source vertex in the graph, find the shortest paths from the source to all the other vertices in the given graph.  

The process of the algorithm:  
1. 每次从未标记的节点中选择距离出发点最近的节点，标记并收录到最优路径集合中
2. 计算刚加入节点A的邻近节点B的距离（不包含标记的节点），若节点A的距离+节点A到节点B的边长之和<节点B的距离，就更新节点B的距离和前面节点  
3. 循环直到目的地被标记  
![Dijkstra's Algorithm](/img/dij.png)  

|Node|Starting Node|Previous Node|
|:---  |:---: |:---:  |  
|0|0||
|1|4|0|
|2|12|1|
|3|19|2|
|4|21|5|
|5|11|6|
|6|9|7|
|7|8|0|
|8|14|2|  

From the table we know that the shortest path from node 0 to 4 is 21, we can also backtrace the path using the previous node from above: `4-5-6-7-0`.