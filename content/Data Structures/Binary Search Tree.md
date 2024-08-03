It is a subset of [[Trees]] where it still contains two children, nodes and root node.
- the left value is **less than or equal** to the parent value
- the right value is **strictly greater** than the parent value


![bst| center](../../assets/bst.svg)
<div style="text-align: center">
  BST example
</div>


- As there is a structure in terms of value (greater/less) it is extremely useful for sorting purposes and efficient searching properties.
- Insertion and Deletion of nodes is very efficient (point of interest halves the tree everytime)

For tree traversal methods, check [[Tree Traversal]].
## Insertion

Every time we try to insert, we have a condition to check: if `current value <= node value` *go left*. If greater, *go right*. Additionally, we need two inputs - **root** and **value to be entered**.
