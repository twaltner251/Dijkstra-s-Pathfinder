# Java Graph Mapping & Pathfinding App

Engineered a geographic routing application utilizing **Dijkstra's algorithm** and a **custom PriorityQueue** to compute shortest paths with a custom graph data structure and **Haversine distance calculations**.

- **Author:** Tyler Waltner  
- **Date:** December 5, 2025  

<img width="600" height="auto" alt="Map Overview Screenshot" src="https://github.com/user-attachments/assets/8c5a7178-371d-4f23-8eeb-092cfcda2da9" />
<img width="600" height="auto" alt="Pathfinding Calculation Screenshot" src="https://github.com/user-attachments/assets/354a5554-7c3f-46f0-959e-7099a4352736" />

---

## 📖 Overview

This project is a Java-based mapping and pathfinding application. It parses map data from text files, constructs a custom graph representation of intersections and roads, calculates the shortest path between two geographic points using Dijkstra's algorithm, and visually renders the interactive map using **Java Swing (`JPanel` and `Graphics2D`)**.

---

## 🏗️ Architecture & Class Overview

The project is structured into the following core components:

- **`Intersection.java`**: Represents vertices (intersections) within the graph, storing unique identifiers along with geographic latitude and longitude coordinates.
- **`Road.java`**: Represents directed/undirected edges (roads) connecting intersections, with weight dynamically assigned by geographic distance.
- **`Graph.java`**: The core adjacency-list graph structure storing all intersections and roads, providing interface methods for graph operations and shortest-path calculation.
- **`MyNode.java`**: A lightweight helper object used by the priority queue during Dijkstra's algorithm to pair intersections with tentative distance metrics.
- **`GUI.java`**: Leverages `JPanel` and `Graphics2D` to map geographic coordinates to visual screen pixels and render the interactive interface.
- **`Main.java`**: Main execution class responsible for CLI argument parsing, file reading/parsing, and instantiating the `Graph` and `GUI` pipelines.

---

## 🛠️ Technical Details & Features

### 1. Custom Priority Queue & Binary Heap Implementation
* Implemented a custom binary heap-based priority queue from scratch (avoiding reliance on standard library utilities like `java.util.PriorityQueue`).
* Handled heap-invariant maintainers (`percolateUp` / `percolateDown`) manually to ensure efficient $O(\log V)$ priority updates during path calculation.

### 2. Geospatial Mathematics (Haversine Formula)
* Integrated the **Haversine formula** to calculate the great-circle distance between coordinate pairs ($\text{lat}_1, \text{lon}_1$) and ($\text{lat}_2, \text{lon}_2$).
* Accounts for Earth's spherical curvature, outputting real-world distance metrics as dynamic edge weights for path computation.

### 3. Rendering Pipeline & Coordinate Normalization
* Scaled map data dynamically using screen-coordinate transformation algorithms, converting raw GPS latitude/longitude values directly into pixel coordinates.
* Applied `Graphics2D` `RenderingHints` (`KEY_ANTIALIASING`) for clean vector road network visuals and distinct path highlight overlays.

---

## ⚙️ Challenges & Insights

1. **Custom Priority Queue Implementation:**  
   Building a priority queue from scratch required a strong conceptual grasp of binary min-heap invariants before writing the underlying array indexing math for parent and child nodes (`index * 2`, `index / 2`). Managing heap operations manually was key to optimizing Dijkstra's lookup phase.

2. **CLI String Case-Sensitivity Bug:**  
   During initial testing, execution yielded persistent `"No path found"` errors due to string mismatches between user input arguments (`Hylan Gavett`) and dataset identifiers (`HYLAN GAVETT`). Normalizing CLI inputs via `.toUpperCase()` resolved lookup failures.

---

## 🔒 Policy Notice

Per university academic integrity and course guidelines, the source code for this project is kept private and cannot be publicly posted. This repository serves solely as a documentation portfolio detailing the project structure, design, and usage instructions.

---

## 📚 Resources & References

- **File I/O Parsing:** [Java File Reading Tutorial](https://www.youtube.com/watch?v=eHjbvgw4hsI)
- **Graphics2D Rendering:** [StackOverflow - RenderingHints & Graphics2D Optimization](https://stackoverflow.com/questions/563237/why-are-my-renderinghints-keys-when-applied-to-a-graphics2d-object-not-being-h)
- **Geospatial Distance Math:** [Haversine Formula Tutorial](https://www.youtube.com/watch?v=Vy2X8PTW_mQ)
- **Java Swing Layout:** [JPanel Tutorial](https://www.youtube.com/watch?v=8pEXo1oVWvU)
