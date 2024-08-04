The delete method will be used **recursively** so it is important to remember that each functionality will repeat if called within.

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

As 20 does not have any child, we can simply delete it and return `None`. If we check Case 2 and 3 we see that a better approach is to check if there is any children. If none, then return `None` to the previous recursion call.
## Case 2 : Node has a single child

![bst-delete-singleChild|center](../assets/graphviz(2).svg)
<div style="text-align: center">
  Node containing 20 has a single child
</div>

Now for 20, we have a single child, and 25 is a leaf. Even if 25 wasn't a leaf, as long as 20 just has a single child, it doesn't change the outcome because after the node is deleted the remaining tree beneath is also a valid BST. So we simply 'stick it' up with the previous node.
- Check if there is a left OR right child (confirm just one child)
- Replace it with the bottom BST (return the child of the node removed)
- If no child, Case 1 applies automatically
## Case 3 : Node has 2 children

![bst-delete-2children|center](../assets/graphviz(3).svg)
<div style="text-align: center">
  Root Node (50) has two children, to be replaced by 60
</div>

In this case, if we need to remove the root (50), we *cannot* simply replace it by anything that is referenced immediately. This is because we need to maintain the properties of BST.

This can be done in 2 ways - 
1. Replace value by **greatest** value from **left subtree**
	- This is done by going **left** as many times possible
2. Replace value by **smallest** value from **right subtree**
	- This is done by going **right** as many times possible

In the visual example shown above as well as in the code we will use the second approach, where 60 is the smallest value in the right subtree of the root. If we replace 50 by value of 60, we now have two 60 (repetition). To solve this, this delete method is called recursively on the remaining right tree to eventually delete the extra 60 on the bottom. This is why in worst case, we might need to traverse the *height* of the tree **twice** (once to find the value to replace, another time to delete it).
Therefore the steps become something like this: 
- If node has two children, find the minimum of right subtree
- Replace value with the minimum value found
- Recursively called delete method on the right subtree until extra gets deleted