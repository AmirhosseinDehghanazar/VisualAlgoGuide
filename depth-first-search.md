# 🔍 Depth-First Search (DFS) Algorithm

> **Category:** Graph Traversal Algorithm  
> **Time Complexity:** O(V + E) (where V = vertices, E = edges)  
> **Space Complexity:** O(V)

## 📌 Introduction
Depth-First Search (DFS) is a **graph traversal** algorithm that explores as far as possible along each branch before backtracking. It is commonly used in **pathfinding, cycle detection, and solving puzzles**.

---

## 🎯 How It Works
1. **Start from a source node** and mark it as visited.
2. **Visit an adjacent unvisited node** and repeat the process.
3. **If no unvisited nodes remain**, backtrack to the previous node.
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
Stack: [A] → [B] → [D] → [] → [E] → [] → [C] → [F] → []
Traversal Order: A → B → D → E → C → F
```

---

## 🚀 Code Implementation
### Python Implementation
```python
def dfs(graph, node, visited=set()):
    if node not in visited:
        print(node, end=" → ")
        visited.add(node)
        for neighbor in graph[node]:
            dfs(graph, neighbor, visited)

# Example Usage
graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': [],
    'F': []
}

dfs(graph, 'A')
```

### JavaScript Implementation
```javascript
function dfs(graph, node, visited = new Set()) {
    if (!visited.has(node)) {
        process.stdout.write(node + " → ");
        visited.add(node);
        graph[node].forEach(neighbor => dfs(graph, neighbor, visited));
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

dfs(graph, 'A');
```

---

## 🖼 Visualization
```
Start:  [A]
Stack:  [B, C]
Stack:  [D, E, C]
Stack:  [E, C]
Stack:  [C]
Stack:  [F]
Traversal Completed 🎯
```

---

## 🌍 Real-World Applications
✔️ **Maze Solving & Pathfinding** (e.g., backtracking-based solutions)  
✔️ **Topological Sorting** (used in dependency resolution)  
✔️ **Cycle Detection in Graphs** (important in deadlock detection)  
✔️ **Solving Puzzles** (e.g., Sudoku solvers, n-queens problem)

---

## 🎨 Design & Customization
- ✅ **Syntax highlighting** for readability.
- ✅ **Graph diagrams & ASCII representations** for better visualization.
- ✅ **Multi-language support** (Python & JavaScript).
- ✅ **Performance analysis** for deeper understanding.

---

## 🏆 Summary
Depth-First Search (DFS) is an essential algorithm in graph theory. By exploring deeply before backtracking, it efficiently solves problems in **pathfinding, topological sorting, and AI applications**.

🌟 **If you found this useful, give it a ⭐ on GitHub!**
