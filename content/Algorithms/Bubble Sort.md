
Bubble Sort is a simple sorting algorithm that repeatedly steps through a list of elements, compares each pair of *adjacent* items, and swaps them if they are in the wrong order. This process continues until no more swaps are needed, meaning the list is sorted. 

The algorithm gets its name (also known as sinking algorithm) because smaller elements "bubble" up to the top (beginning) of the list, while larger elements sink to the bottom with each pass. Think of each pass through the list as shaking a bottle and watching the bubbles rise to the top, leaving the largest bubbles (largest elements) at the end after each pass.

## Notes

- **Process:** The algorithm works by comparing each pair of adjacent elements and swapping them if they are out of order. This is done repeatedly, passing through the list *multiple* times.
  
- **Passes:** Each complete pass through the list guarantees that the largest unsorted element moves to its correct position at the end of the list. 
	-  If there are $n$ elements, we can do at most $n-1$ iterations. This is because we compare element with the next one. If we reach $n^{th}$ element, there's nothing to compare it with.
	- *After the first pass, the largest element is in the correct position, after the second pass, the second-largest element is in the correct position, and so on.*
	- This means every consequent pass checks for one less element than the previous check.

- **Efficiency:** Bubble Sort is not the most efficient sorting algorithm, especially for large lists, because it repeatedly passes through the list even if it's already sorted. However, it's straightforward and easy to understand, making it a good starting point for learning about sorting algorithms.

- **Best Case:** If the list is already sorted, Bubble Sort can recognize this and stop early. In this case, the best time complexity is O(n), where n is the number of elements in the list.

- **Worst Case:** In the worst case, when the list is in reverse order, Bubble Sort will take O(n²) time because it needs to swap each element multiple times to get them in order.

- **Stability:** Bubble Sort is a stable sorting algorithm, meaning that it preserves the relative order of equal elements.
  
- **Space Complexity:** The space complexity of Bubble Sort is O(1) because it only requires a constant amount of additional memory space for the swaps.

## Code

1. Outer loop goes from 0 to $n-1$ because we loop through the whole list of size $n$ one time less than total length
2. Inner loop goes from 0 to $n-1-i$ where $i$ is the outer loop counter. This is to adjust for shortening the window of search by 1 element every iteration


```python

def bubbleSort(array):
    print("Provided array: ")
    print(array)
    length = len(array)
    for i in range(length - 1):
        for j in range(length - 1 - i):
            if array[j] > array[j + 1]:
                array[j], array[j + 1] = array[j + 1], array[j]
    print("Sorted array: ")
    print(array)

```

### Complexities

**Time Complexity:** $\mathcal{O}(n^2)$ 
**Space Complexity:** $\mathcal{O}(1)$  

We loop list of $n$ items $n$ times each so order is $\mathcal{O}(n^2)$ . As we do the swaps in-order, the space complexity is $\mathcal{O}(1)$ . 