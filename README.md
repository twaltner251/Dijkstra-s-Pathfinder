# Java Graph Mapping & Pathfinding App

* **Author:** Tyler Waltner

<img width="600" height="auto" alt="Screenshot 2025-12-08 at 1 28 45 AM" src="https://github.com/user-attachments/assets/8c5a7178-371d-4f23-8eeb-092cfcda2da9" />
<img width="600" height="auto" alt="Screenshot 2025-12-08 at 1 26 17 AM" src="https://github.com/user-attachments/assets/354a5554-7c3f-46f0-959e-7099a4352736" />

* **Date:** December 5, 2025

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

Policy Notice: Per university academic integrity and course guidelines, the source code for this project is kept private and cannot be publicly posted. This repository serves solely as a documentation portfolio detailing the project structure, design, and usage instructions.
