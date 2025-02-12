# ⚡ Quick Sort Algorithm

> **Category:** Sorting Algorithm  
> **Time Complexity:** O(n log n) (average case), O(n²) (worst case)  
> **Space Complexity:** O(log n) (due to recursion stack)

## 📌 Introduction
Quick Sort is a **divide-and-conquer** algorithm that sorts an array by selecting a pivot, partitioning elements into smaller and larger subarrays, and recursively sorting the subarrays.

---

## 🎯 How It Works
1. **Choose a pivot** (commonly the last element, first element, or a random element).
2. **Partition** the array so that:
   - Elements smaller than the pivot move to the left.
   - Elements larger than the pivot move to the right.
3. Recursively apply Quick Sort to the left and right subarrays.
4. Combine sorted parts to get the final sorted array.

### 📊 Example Walkthrough
#### Given Array:
```
[8, 3, 1, 7, 0, 10, 2]
```
Choose pivot **2**:
```
Left:  [0, 1]
Pivot: [2]
Right: [8, 3, 7, 10]
```
Repeat sorting for left and right subarrays recursively.

---

## 🚀 Code Implementation
### Python Implementation
```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + middle + quick_sort(right)

# Example Usage
arr = [8, 3, 1, 7, 0, 10, 2]
print("Sorted Array:", quick_sort(arr))
```

### JavaScript Implementation
```javascript
function quickSort(arr) {
    if (arr.length <= 1) return arr;
    const pivot = arr[Math.floor(arr.length / 2)];
    const left = arr.filter(x => x < pivot);
    const middle = arr.filter(x => x === pivot);
    const right = arr.filter(x => x > pivot);
    return [...quickSort(left), ...middle, ...quickSort(right)];
}

// Example Usage
const arr = [8, 3, 1, 7, 0, 10, 2];
console.log("Sorted Array:", quickSort(arr));
```

---

## 🖼 Visualization
```
Initial:  [8, 3, 1, 7, 0, 10, 2]
Choose Pivot: 2
Left:  [0, 1]  | Pivot: [2]  | Right: [8, 3, 7, 10]
Continue Sorting Recursively...
```

---

## 🌍 Real-World Applications
✔️ Used in **search engines** to sort search results efficiently.
✔️ Applied in **databases** for sorting large datasets.
✔️ Used in **computer graphics** for object sorting (e.g., rendering order).
✔️ Popular in **game development** for sorting game objects.

---

## 🎨 Design & Customization
- ✅ **Syntax highlighting** for readability.
- ✅ **Tables, Icons, and ASCII diagrams** for clear visualization.
- ✅ **Multi-language support** (Python & JavaScript).
- ✅ **Performance analysis** for deeper understanding.

---

## 🏆 Summary
Quick Sort is one of the most efficient sorting algorithms, commonly used in real-world applications. It works on the principle of partitioning and recursion, achieving **O(n log n)** on average.

🌟 **If you found this useful, give it a ⭐ on GitHub!**
