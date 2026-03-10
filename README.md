# 🌳 Subtree of Another Binary Tree (Java)

## 📌 Overview

This project demonstrates how to determine whether **one binary tree is a subtree of another binary tree** using **recursion in Java**.

A tree **T2** is considered a subtree of **T1** if there exists a node in **T1** such that the subtree rooted at that node is **identical to T2**.

This is a common **Binary Tree interview problem** that helps in understanding **tree comparison and recursive traversal**.

---

# 🌿 Example

### Main Tree

```id="tree_main"
        1
       / \
      2   3
     / \  / \
    4  5 6   7
```

### Subtree

```id="tree_sub"
      2
     / \
    4   5
```

Since this structure appears inside the main tree, the output will be:

```id="output"
true
```

---

# 📏 Problem Statement

Given two binary trees:

* **Root** → main tree
* **SubRoot** → potential subtree

Determine whether **SubRoot exists inside Root as a subtree**.

---

# ⚙️ Algorithm

The solution works in two main steps:

### 1️⃣ Check Every Node

Traverse the main tree and check if the current node could be the root of the subtree.

```id="step1"
If root.data == subroot.data
    check if both trees are identical
```

---

### 2️⃣ Check Tree Structure

If the node values match, verify whether the **entire subtree structure and values are identical**.

This is done using the `isIdentical()` function.

---

# 💻 Java Implementation

### Check if Subtree Exists

```java id="code1"
public static boolean isSubtree(Node root, Node subroot){
    if(root == null){
        return false;
    }

    if(root.data == subroot.data){
        if(isIdentical(root, subroot)){
            return true;
        }
    }

    boolean left = isSubtree(root.left, subroot);
    boolean right = isSubtree(root.right, subroot);

    return left || right;
}
```

---

### Check if Two Trees Are Identical

```java id="code2"
public static boolean isIdentical(Node node, Node subroot){
    if(node == null && subroot == null){
        return true;
    }

    if(node == null || subroot == null || node.data != subroot.data){
        return false;
    }

    if(!isIdentical(node.left, subroot.left)){
        return false;
    }

    if(!isIdentical(node.right, subroot.right)){
        return false;
    }

    return true;
}
```

---

# ▶️ Program Output

```id="result"
true
```

This means the **second tree is a subtree of the first tree**.

---

# ⏱ Time and Space Complexity

| Complexity       | Value    |
| ---------------- | -------- |
| Time Complexity  | O(n × m) |
| Space Complexity | O(h)     |

Where:

* **n** = number of nodes in main tree
* **m** = number of nodes in subtree
* **h** = height of the tree (recursion stack)

---

# 🧠 Concepts Used

* 🌳 Binary Trees
* 🔁 Recursion
* 🔍 Tree Traversal
* 🧩 Tree Comparison
* ⚡ Divide and Conquer

---

# 🎯 Learning Outcomes

After completing this program you will understand:

✔ How to compare two binary trees
✔ How to detect a subtree inside another tree
✔ How recursion works in complex tree problems
✔ Tree traversal strategies

These concepts are important for **Data Structures and Algorithms (DSA)** and **technical interviews**.

---

