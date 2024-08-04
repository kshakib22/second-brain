The delete method will be used recursively so it is important to remember that each functionality will repeat if called within.

There are three main cases to consider while deleting a node from BST:
1. Node to be deleted is a leaf node
2. Node has one child
3. Node has two children
Although the last one might vary in complexity, it will be solved by calling delete recursively as we will see in the following sections.

## Case 1 : Node is a leaf

![bst-delete-leaf|center](../assets/graphviz(1).svg)
<div style="text-align: center">
Node containing 20 is a leaf
</div>
