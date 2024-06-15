Recursive functions are a powerful programming concept that involve a function calling itself. Usually used to break down bigger problems into smaller problems.  The smaller problems are **identical** to each other and combine to form the final answer.

This  basically sounds like an infinite loop (function calling itself, when does it stop?). It *is* an infinite loop that’s why the **base case** exists to end it. Base case is a simple condition that can be solved directly without further recursion. Base case  $\rightarrow$  no recursion needed $=$ Infinite loop ended.

## Mathematical Recursion

What helps me is mathematically defining the problem in terms of function definition. Let's consider sum of numbers from $1$ till $n$ (taken as input).
$$
F_n = n + F_{n-1}
$$
This will keep moving backwards even with negative numbers, indefinitely. But we want to stop when it reaches 0. After that point negative number will keep reducing the sum (unless that's required). This is our base case. So we further define it including our base case as such (beside the $\mid$ sign):
$$
F_n = n+F_{n-1} \mid n \in \mathbb{Z} \text{ and } n > 0
$$
Meaning $n$ is an integer AND is greater than 0 (also known as counting numbers/natural numbers).

To ensure $n$ is integer $\rightarrow$ start with integer, decrement by 1 (stays integer).
To ensure greater than 0 $\rightarrow$ put a control (if statement) to return when 0. Actually we can just return when its 1 because 0 doesn't change anything in our case. If you *really* want to be specific, this is what's up:
$$
F_n = n+F_{n-1} \mid n \in \mathbb{Z} \text{ and } n \geq 1
$$
Now convert all these into analogous parts of code where $F_n$ is a function, $n$ is our input.
```run-python
def Fn(n):
  if n == 1:
      return 1
  result = n + Fn(n-1)
  return result
print(Fn(10))
```
