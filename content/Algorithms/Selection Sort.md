
Selection Sort is a simple comparison-based sorting algorithm. It works by repeatedly selecting the smallest (or largest, depending on the sorting order) element from the unsorted portion of the list and moving it to the sorted portion. This process is repeated until the entire list is sorted.

The name "Selection Sort" comes from the way the algorithm works—it repeatedly **selects** the smallest element from the unsorted part of the array and places it in its correct position in the sorted part. This helps in remembering that the algorithm's key operation is selecting the minimum (or maximum) value during each pass.

## Notes

1. **Initial Setup**:
   - Divide the array into two parts: a sorted portion and an unsorted portion. Initially, the sorted portion is empty, and the unsorted portion contains the entire list.

2. **Selection Process**:
   - Start with the first element in the unsorted portion as the "current minimum."
   - Compare this "current minimum" with the rest of the elements in the unsorted portion to find the actual minimum element.

3. **Swapping**:
   - Once the minimum element is found, swap it with the first element of the unsorted portion. This element is now part of the sorted portion.

4. **Repeat**:
   - Move the boundary between the sorted and unsorted portions one element to the right, and repeat the selection and swapping process for the remaining unsorted portion.

5. **Completion**:
   - The algorithm continues until the unsorted portion is empty, meaning the entire list is now sorted.

## Characteristics

- **Time Complexity**:
  - The time complexity of Selection Sort is $O(n^2)$ because it involves two nested loops: one to traverse the array and another to find the minimum element in the unsorted portion.
  
- **Space Complexity**:
  - Selection Sort is an **in-place** sorting algorithm, meaning it requires only a constant amount of additional memory space, $O(1)$

- **Stability**:
  - Selection Sort is **not a stable** sorting algorithm. 
  
- **Best Use Cases**:
  - Selection Sort is best used when the memory is limited, as it requires minimal additional space. However, due to its time complexity, it is generally inefficient for large lists and is primarily used in educational contexts.

## Code

1. Step 1


```python
enter code here

```

### Complexities

**Time Complexity:** $\mathcal{O}(\log n)$ 
**Space Complexity:** $\mathcal{O}(n)$  