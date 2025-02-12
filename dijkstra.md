# 🚀 Dijkstra's Algorithm

> **Category:** Pathfinding Algorithm  
> **Time Complexity:** O((V + E) log V)  
> **Space Complexity:** O(V)

## 📌 Introduction
Dijkstra's Algorithm is a **greedy algorithm** used to find the **shortest path** between nodes in a weighted graph. It is widely used in **routing protocols, GPS navigation, and network optimizations**.

---

## 🎯 How It Works
1. **Initialize:** Set the starting node's distance to 0 and all others to infinity.
2. **Choose the smallest known distance node** and mark it as visited.
3. **Update the distances** of its adjacent nodes if a shorter path is found.
4. **Repeat until all nodes are visited** or the shortest path to the target is determined.

### 📊 Example Walkthrough
#### Given Graph:
```
    (A)
   /   \
  4     1
 /       \
(B) --3-- (C)
  \       /
   2     5
    \   /
     (D)
```

**Starting from A:**
```
A → B (4), C (1)
C → D (6)
B → D (6, shorter path found)
Final Distances: A(0), B(4), C(1), D(6)
```

---

## 🚀 Code Implementation
### Python Implementation
```python
import heapq

def dijkstra(graph, start):
    pq = []
    heapq.heappush(pq, (0, start))
    distances = {node: float('inf') for node in graph}
    distances[start] = 0
    
    while pq:
        current_distance, current_node = heapq.heappop(pq)
        
        if current_distance > distances[current_node]:
            continue
        
        for neighbor, weight in graph[current_node]:
            distance = current_distance + weight
            if distance < distances[neighbor]:
                distances[neighbor] = distance
                heapq.heappush(pq, (distance, neighbor))
    
    return distances

# Example Usage
graph = {
    'A': [('B', 4), ('C', 1)],
    'B': [('A', 4), ('D', 2), ('C', 3)],
    'C': [('A', 1), ('B', 3), ('D', 5)],
    'D': [('B', 2), ('C', 5)]
}

print(dijkstra(graph, 'A'))
```

### JavaScript Implementation
```javascript
class PriorityQueue {
    constructor() {
        this.queue = [];
    }
    enqueue(node, priority) {
        this.queue.push({ node, priority });
        this.queue.sort((a, b) => a.priority - b.priority);
    }
    dequeue() {
        return this.queue.shift().node;
    }
    isEmpty() {
        return this.queue.length === 0;
    }
}

function dijkstra(graph, start) {
    let distances = {};
    let pq = new PriorityQueue();
    Object.keys(graph).forEach(node => distances[node] = Infinity);
    distances[start] = 0;
    pq.enqueue(start, 0);
    
    while (!pq.isEmpty()) {
        let currentNode = pq.dequeue();
        for (let [neighbor, weight] of graph[currentNode]) {
            let distance = distances[currentNode] + weight;
            if (distance < distances[neighbor]) {
                distances[neighbor] = distance;
                pq.enqueue(neighbor, distance);
            }
        }
    }
    return distances;
}

// Example Usage
const graph = {
    A: [['B', 4], ['C', 1]],
    B: [['A', 4], ['D', 2], ['C', 3]],
    C: [['A', 1], ['B', 3], ['D', 5]],
    D: [['B', 2], ['C', 5]]
};

console.log(dijkstra(graph, 'A'));
```

---

## 🖼 Visualization
```
Start:  [A: 0]
Queue:  [C: 1, B: 4]
Queue:  [B: 4, D: 6]
Queue:  [D: 6]
Final Distances: A(0), B(4), C(1), D(6)
Traversal Completed 🎯
```

---

## 🌍 Real-World Applications
✔️ **GPS Navigation Systems** (e.g., Google Maps, Waze)  
✔️ **Network Routing Protocols** (e.g., OSPF)  
✔️ **Game AI Pathfinding** (e.g., A* heuristic-based enhancements)  
✔️ **Supply Chain Optimization** (e.g., shortest delivery paths)

---

## 🎨 Design & Customization
- ✅ **Graph diagrams & ASCII representations** for clarity.
- ✅ **Multi-language support** (Python & JavaScript).
- ✅ **Priority Queue Implementation** for efficiency.
- ✅ **Performance analysis** for deeper understanding.

---

## 🏆 Summary
Dijkstra's Algorithm is fundamental in graph theory. By leveraging a **priority queue**, it efficiently determines **shortest paths** in real-world applications like **navigation, networking, and AI**.

🌟 **If you found this useful, give it a ⭐ on GitHub!**
