---
title: "Node Coloring"
date: 2023-03-07T12:48:33-08:00
draft: False
---
I learned something interesting today. I was solving a problem called
"All Paths from Source Lead to Destination" and comparing it to
"Find if Path Exists in Graph". Both problems are very similar because they
both require you to find a path from a source to a destination in a graph.
The latter requires me to finf if "any" path exists, but the former is slightly
hard because I have to find whether "all" paths lead to a destination.
I say tricky because the former requires "node coloring". To find a single
path, I can detect a cycle by adding the visited nodes and checking to see if
I'm revisiting them or not. When a node is visited, I know that path will not
get me to the destination. But in order to see if all paths are valid, I have
to reivisit a node. I need to recursively check all children nodes to see if 
the paths lead to the destination, so I can't simply check if I visited it 
or not. I could've already visited the path that leads to the destination
and that is fine. So I need a way to detect a cycle while removing the paths
that are definitely not possible.

This can be done through node color. White is an univisited node, Gray is a
visiting node, and black is a visited processed node. If the node is white,
we recursively travel through. If the node is black, we know that the paths
do not lead to the destination. If the node is gray, we know we have a cycle.

