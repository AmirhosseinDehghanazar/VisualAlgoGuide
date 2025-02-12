# 🔍 Binary Search Algorithm

> **Category:** Searching Algorithm  
> **Time Complexity:** O(log n)  
> **Space Complexity:** O(1)

## 📌 Introduction
Binary Search is a highly efficient algorithm used to find an element in a **sorted array**. It works by repeatedly dividing the search interval in half. If the target element is smaller than the middle element, the search continues in the left half; otherwise, it continues in the right half.

---

## 🎯 How It Works
1. **Find the middle element** of the array.
2. **Compare** the target with the middle element:
   - If it matches, return the index.
   - If the target is smaller, search in the left half.
   - If the target is larger, search in the right half.
3. Repeat the process until the element is found or the array is empty.

### 📊 Example Walkthrough
#### Given Array (Sorted):
```
[2, 4, 7, 10, 15, 20, 25]
```
Searching for **10**:
```
Iteration 1: Middle element = 10 (Found ✅)
```
Searching for **15**:
```
Iteration 1: Middle element = 10 (Too low)
Iteration 2: Search right half [15, 20, 25], Middle = 20 (Too high)
Iteration 3: Search left half [15], Middle = 15 (Found ✅)
```

---

## 🚀 Code Implementation
### Python Implementation
```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1

# Example Usage
arr = [2, 4, 7, 10, 15, 20, 25]
target = 10
result = binary_search(arr, target)
print(f"Element found at index: {result}")
```

### JavaScript Implementation
```javascript
function binarySearch(arr, target) {
    let left = 0, right = arr.length - 1;
    while (left <= right) {
        let mid = Math.floor((left + right) / 2);
        if (arr[mid] === target) return mid;
        else if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}

// Example Usage
const arr = [2, 4, 7, 10, 15, 20, 25];
console.log("Element found at index:", binarySearch(arr, 10));
```

---

## 🖼 Visualization
```
Initial: [2, 4, 7, 10, 15, 20, 25]
         ^        ^        ^
         L        M        R

Step 1: Compare middle element 10 with target.
Step 2: Found! 🎯
```

---

## 🌍 Real-World Applications
✔️ Used in databases for indexing (e.g., **B-Trees in SQL databases**)
✔️ Search functionality in **large-scale applications** (Google, Amazon, etc.)
✔️ Applied in **computer graphics** for finding elements efficiently

---

## 🎨 Design & Customization
- ✅ **Syntax highlighting** for better readability
- ✅ **Tables, Icons, and ASCII diagrams** for better visualization
- ✅ **Multiple language support** (Python & JavaScript)
- ✅ **Performance analysis** for complexity understanding

---

## 🏆 Summary
Binary Search is a fundamental algorithm for fast searching in sorted arrays. By cutting the search space in half with each step, it achieves an impressive **O(log n)** time complexity, making it far superior to linear search for large datasets!

🌟 **If you found this useful, give it a ⭐ on GitHub!**
