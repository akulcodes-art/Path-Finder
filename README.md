
## **Pathfinder App**  

### **Overview**  
The Pathfinder App is an interactive visualization tool that helps users find the shortest or most efficient path from a start point to a destination in a grid-based maze. The application supports multiple pathfinding algorithms, allowing users to compare their performance in real time.  

### **Features**  
✅ Interactive grid-based interface  
✅ Selectable start and end points  
✅ Obstacle placement for complex mazes  
✅ Real-time visualization of pathfinding algorithms  
✅ Multiple algorithm support: **Dijkstra, A* (A-star), BFS, DFS**  
✅ Performance comparison and time analysis  

### **Tech Stack**  
- **Frontend:** React.js, TypeScript, Tailwind CSS  
- **Backend (optional, if applicable):** Node.js, Express.js  
- **Algorithms Implementation:** JavaScript/TypeScript  

---

## **Algorithms Used**  

### **1. Dijkstra's Algorithm (Shortest Path in Weighted Graphs)**  
**Concept:**  
- Dijkstra's algorithm finds the shortest path from the start node to all other nodes in a graph with non-negative weights.  
- It uses a **priority queue** (or min-heap) to always expand the least costly node first.  

**Steps:**  
1. Initialize all nodes with infinite distance, except the start node (0 distance).  
2. Use a priority queue to process the node with the smallest known distance.  
3. Update the distances of its neighbors if a shorter path is found.  
4. Repeat until the destination node is reached or all nodes are processed.  

**Best Use Case:**  
- When all edges have positive weights (e.g., roads with distances).  

---

### **2. A* (A-star) Algorithm (Heuristic-Based Shortest Path Search)**  
**Concept:**  
- A* improves upon Dijkstra’s algorithm by using a heuristic function \( f(n) = g(n) + h(n) \), where:  
  - \( g(n) \) is the cost from the start node to node \( n \).  
  - \( h(n) \) is the estimated cost from \( n \) to the goal (heuristic function, usually Manhattan distance in grids).  

**Steps:**  
1. Initialize the start node with \( f(n) = 0 + h(n) \).  
2. Use a priority queue to expand the node with the lowest \( f(n) \) value.  
3. Update its neighbors' \( g(n) \) values if a better path is found.  
4. Repeat until the destination is reached.  

**Best Use Case:**  
- When a heuristic function can guide the search efficiently (e.g., real-world navigation systems).  

---

### **3. Breadth-First Search (BFS) (Unweighted Shortest Path)**  
**Concept:**  
- BFS is a graph traversal algorithm that explores all neighbors at the current depth before moving deeper.  
- It guarantees the shortest path in an **unweighted graph**.  

**Steps:**  
1. Start from the source node and enqueue it.  
2. Dequeue a node and visit all its unvisited neighbors, marking them as visited.  
3. Continue until the destination is found or the queue is empty.  

**Best Use Case:**  
- When all moves have equal weight (e.g., a chessboard or a simple grid-based game).  

---

### **4. Depth-First Search (DFS) (Pathfinding Without Optimality Guarantee)**  
**Concept:**  
- DFS explores as far as possible along each branch before backtracking.  
- It does not guarantee the shortest path but is useful for exploring mazes.  

**Steps:**  
1. Start from the source and mark it as visited.  
2. Recursively visit each unvisited neighbor.  
3. Backtrack if no more moves are available.  

**Best Use Case:**  
- When finding **any** path is more important than finding the shortest one (e.g., puzzle-solving, AI exploration).  

---

## **Performance Comparison**  

| Algorithm | Guarantees Shortest Path? | Suitable for Weighted Graphs? | Time Complexity   |
|-----------|-------------------------|---------------------------|-------------------------|
| Dijkstra  | ✅ Yes                  |          ✅ Yes            | \( O((V + E) \log V) \) |
| A* (A-star) | ✅ Yes | ✅ Yes | \( O((V + E) \log V) \) |
| BFS | ✅ Yes (only for unweighted) | ❌ No | \( O(V + E) \) |
| DFS | ❌ No | ❌ No | \( O(V + E) \) |

---

## **Possible Enhancements**  
🔹 Allow users to draw custom mazes.  
🔹 Add more heuristic functions for A*.  
🔹 Optimize Dijkstra’s algorithm using a **Fibonacci heap**.  
🔹 Implement bi-directional search for faster pathfinding.  

---
