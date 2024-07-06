---
title: Introduction
draft: false
tags: 
date:
---
This page is an experimental page where different aspects of notes can be sanity-checked.

# Lorem Ipsum (h1)

**Lorem Ipsum** is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

Testing a code snippet with a binary search for Python.

``` python
def binary_search(arr, low, high, x):
  """
  Performs a binary search on a sorted list.

  Args:
      arr: The sorted list to search.
      low: The lower bound of the search space (inclusive).
      high: The upper bound of the search space (inclusive).
      x: The element to search for.

  Returns:
      The index of the element in the list if found, otherwise -1.
  """

  if low > high:
    return -1

  mid = (low + high) // 2

  if arr[mid] == x:
    return mid

  elif arr[mid] < x:
    return binary_search(arr, mid + 1, high, x)

  else:
    return binary_search(arr, low, mid - 1, x)

# Example usage
arr = [2, 3, 4, 10, 40]
x = 10

result = binary_search(arr, 0, len(arr) - 1, x)

if result != -1:
  print("Element is present at index", str(result))
else:
  print("Element is not present in array")

```

Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.

Now lets try a latex snippet for Euler's GCD algorithm using [[LaTeX]].

## GCD Algorithm (h2)

The following algorithm computes the greatest common divisor (GCD) of two non-negative integers $a$ and  $b$.  The formula is **wrong** btw.


$$
\begin{equation}
\mathrm{gcd}(a, b) = \begin{cases}
    b & \text{if } b = 0 \\
    \mathrm{gcd}(b, {rem}(a, b)) & \text{otherwise}
\end{cases}
\end{equation}
$$

### Explanation (h3)

The algorithm repeatedly replaces \(a\) with \(b\) and \(b\) with the remainder of \(a\) divided by \(b\) until \(b\) becomes zero. The final value of \(a\) is the greatest common divisor.

Random Picture time!

![](Pasted%20image%2020240610051047.png)

#### Highlighter testing (h4)

Highlight using double equals wrapping like `==text==`. ==This text should be highlighted==.