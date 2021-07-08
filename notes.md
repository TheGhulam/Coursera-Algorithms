# Week 1

## [Union-Find](./week1/UnionFind.pdf)

### Dynamic Connectivity
Given a set of N objects:
- Union command
- Find/connected query

Modelling the connections:  
We assume "is connected to" is an equivalence relation:
- Reflexive: p is connected to p.
- Symmetric: if p is connected to q, then q is connected to p.
- Transitive: if p is connected to q and q is connected to r, then p is connected to r

### Quick Find
Data Structure  
- Integer array id[] of size N.
- Interpretation: p and q are connected if they have the same id.

Find: Check if p and q have the same id  
Union: To merge components containing p and q, change all ids of q to id[p]  
>Quick find is too slow for big problems (Quadratic)

Defects
- Union too expensive (N array accesses).
- Trees are flat, but too expensive to keep them flat.

### Quick Union
Data Structure  
- Integer array id[] of size N.
- Interpretation: id[i] is parent of i.
- **Root** of i is id[id[id[...id[]...]]]

Find: Check if p and q have the same root  
Union: To merge components containing p and q, set the id of p's root to the d of q's root

Defects  
- Trees can get tall
- Find too expensive (could by N array accesses)

### Quick Union improvements
Weighted quick-union
- Modify quick-union to avoid tall trees.
- Keep track of size of each tree (number of objects)
- Balance by linking root of smaller tree to root of larger tree.
# Week 2
