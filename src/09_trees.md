Tree is a non linear data structure


**binary search tree**

Binary search tree, left sub tree contain which are less than root node and the right sub tree consist of values which are greater than the root node.

time complexity is O(n)

class Node:
    data  // value stored in the node
    left  // reference to the left child
    right // reference to the right child

class BinaryTree:
    function insert(root, value):
        if root is NULL:
            return new Node(value)
        if value < root.data:
            root.left = insert(root.left, value)
        else:
            root.right = insert(root.right, value)
        return root

    function search(root, value):
        if root is NULL or root.data == value:
            return root
        if value < root.data:
            return search(root.left, value)
        return search(root.right, value)

    function inorder(root):
        if root is not NULL:
            inorder(root.left)
            print(root.data)
            inorder(root.right)

    function preorder(root):
        if root is not NULL:
            print(root.data)
            preorder(root.left)
            preorder(root.right)

    function postorder(root):
        if root is not NULL:
            postorder(root.left)
            postorder(root.right)
            print(root.data)

    function delete(root, value):
        if root is NULL:
            return root
        if value < root.data:
            root.left = delete(root.left, value)
        else if value > root.data:
            root.right = delete(root.right, value)
        else:
            if root.left is NULL:
                return root.right
            if root.right is NULL:
                return root.left
            temp = findMin(root.right)
            root.data = temp.data
            root.right = delete(root.right, temp.data)
        return root

    function findMin(node):
        while node.left is not NULL:
            node = node.left
        return node

// Example Usage
binaryTree = BinaryTree()
root = NULL
root = binaryTree.insert(root, 10)
root = binaryTree.insert(root, 5)
root = binaryTree.insert(root, 15)
binaryTree.inorder(root)   // Outputs: 5 10 15
binaryTree.search(root, 5) // Returns the node with value 5
root = binaryTree.delete(root, 5)
binaryTree.inorder(root)   // Outputs: 10 15



