# 🔍 Breadth-First Search (BFS) Algorithm

> **Category:** Graph Traversal Algorithm  
> **Time Complexity:** O(V + E) (where V = vertices, E = edges)  
> **Space Complexity:** O(V)

## 📌 Introduction
Breadth-First Search (BFS) is a **graph traversal** algorithm that explores all **neighboring nodes** before moving to the next level. It is commonly used in **shortest path** problems and AI applications.

---

## 🎯 How It Works
1. **Start from a source node** and enqueue it.
2. **Mark the node as visited** to avoid reprocessing.
3. **Dequeue a node**, explore all its neighbors, and enqueue them.
4. Repeat until all nodes have been visited.

### 📊 Example Walkthrough
#### Given Graph:
```
     A
    / \
   B   C
  / \   \
 D   E   F
```
**Starting from A:**
```
Queue: [A] → [B, C] → [C, D, E] → [D, E, F] → [E, F] → [F] → []
Traversal Order: A → B → C → D → E → F
```

---

## 🚀 Code Implementation
### Python Implementation
```python
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])
    
    while queue:
        node = queue.popleft()
        if node not in visited:
            print(node, end=" → ")
            visited.add(node)
            queue.extend(graph[node])

# Example Usage
graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': [],
    'F': []
}

bfs(graph, 'A')
```

### JavaScript Implementation
```javascript
function bfs(graph, start) {
    let visited = new Set();
    let queue = [start];
    
    while (queue.length > 0) {
        let node = queue.shift();
        if (!visited.has(node)) {
            process.stdout.write(node + " → ");
            visited.add(node);
            queue.push(...graph[node]);
        }
    }
}

// Example Usage
const graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': [],
    'F': []
};

bfs(graph, 'A');
```

---

## 🖼 Visualization
```
Start:  [A]
Queue:  [B, C]
Queue:  [C, D, E]
Queue:  [D, E, F]
Queue:  [E, F]
Queue:  [F]
Traversal Completed 🎯
```

---

## 🌍 Real-World Applications
✔️ **Shortest Path Algorithms** (e.g., Dijkstra’s Algorithm uses BFS in unweighted graphs)  
✔️ **Social Networks** (e.g., finding the shortest connection between people)  
✔️ **Web Crawlers** (searching through linked websites efficiently)  
✔️ **AI & Game Development** (solving mazes, pathfinding in grid-based maps)

---

## 🎨 Design & Customization
- ✅ **Syntax highlighting** for readability.
- ✅ **Graph diagrams & ASCII representations** for better visualization.
- ✅ **Multi-language support** (Python & JavaScript).
- ✅ **Performance analysis** for deeper understanding.

---

## 🏆 Summary
Breadth-First Search (BFS) is a fundamental traversal technique in graph theory. By systematically visiting each node level by level, it ensures efficient exploration and is widely used in **shortest path problems, AI, and network analysis**.

🌟 **If you found this useful, give it a ⭐ on GitHub!**
