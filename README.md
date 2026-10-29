# Java Graph Mapping & Pathfinding App

* **Author:** Tyler Waltner
* **Date:** December 5, 2025
<img width="600" height="auto" alt="Screenshot 2025-12-08 at 1 28 45 AM" src="https://github.com/user-attachments/assets/8c5a7178-371d-4f23-8eeb-092cfcda2da9" />
<img width="600" height="auto" alt="Screenshot 2025-12-08 at 1 26 17 AM" src="https://github.com/user-attachments/assets/354a5554-7c3f-46f0-959e-7099a4352736" />



---

## Overview

This project is a Java-based mapping and pathfinding application. It reads map data from text files, constructs a graph representation of intersections and roads, calculates the shortest path between two points using **Dijkstra's algorithm**, and visually renders the map using **Java Swing (`JPanel` and `Graphics2D`)**. 

---

## Architecture & Class Overview

The project is structured into the following core classes:

* **`Intersection.java`**: Represents all vertices (intersections) within the graph.
* **`Road.java`**: Represents all edges (roads) connecting the intersections.
* **`Graph.java`**: The core graph object representing the overall map, storing all intersections and roads.
* **`MyNode.java`**: A lightweight helper class utilized by the priority queue during the implementation of Dijkstra's algorithm in `Graph.java`.
* **`GUI.java`**: Utilizes `JPanel` and `Graphics2D` to render and display the interactive map interface on the user's screen.
* **`Main.java`**: The centerpiece execution class responsible for file reading and initializing instances of the `Graph` and `GUI` classes.

---

Challenges Faced:
Implementing custom Prio-Q from scratch was a key learning challenge for me, I had to first conceptually wrap my head around all functions of a Prio-Q and then go on to implement each function one by one.
I spent 20-30mins 'bugfixing' trying to find why my program was constantly outputting "No path found" and it wasn't able to even identify the starting or ending intersections.
But it turned out to be a user error where I was typing in the intersection names of ur.txt in camel case instead of uppercase. 
Example of what I typed in: 
java Main.java ur.txt --show --directions Hylan Gavett 

While ur.txt has all of the named intersections in uppercase so all I had to type in was:
java Main.java ur.txt --show --directions HYLAN GAVETT

I felt very silly after finding this out...

---

Policy Notice: Per university academic integrity and course guidelines, the source code for this project is kept private and cannot be publicly posted. This repository serves solely as a documentation portfolio detailing the project structure, design, and usage instructions.

---

Some tutorials/external help I consulted on this lab were the following:
File Reading - https://www.youtube.com/watch?v=eHjbvgw4hsI
Graphics2d rendering help - https://stackoverflow.com/questions/563237/why-are-my-renderinghints-keys-when-applied-to-a-graphics2d-object-not-being-h
Haversine forumla - https://www.youtube.com/watch?v=Vy2X8PTW_mQ
JPanel tutorial - https://www.youtube.com/watch?v=8pEXo1oVWvU
