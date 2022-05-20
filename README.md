# Numpy-and-Cosine-Operations
A repo that implements some basic operations on numpy arrays and cosine similarity in machine learning.

 ## 1. Finding number of triangles in an undirected graph using Numpy operations
 The implementation of this problem as been done in the `Triangle_Count_Numpy.ipynb` file.
 
We will find the number of triangles by representing the graph as a adjacency matrix.

Let $A$ be the _adjacency matrix_ representation of the graph, defined as follows. The entries of $A$ are either 0 or 1; and $a_{i,j}$ equals 1 if and only if there is an edge connecting nodes $i$ and $j$. For instance, for the graph shown above,

$$
A = \begin{bmatrix}
        0 & 1 & 0 & 1 & 0 & 1 \\
        1 & 0 & 0 & 1 & 0 & 0 \\
        0 & 0 & 0 & 1 & 0 & 0 \\
        1 & 1 & 1 & 0 & 1 & 1 \\
        0 & 0 & 0 & 1 & 0 & 0 \\
        1 & 0 & 0 & 1 & 0 & 0
    \end{bmatrix}.
$$

Observe that the relationships are symmetric. For instance, 0 and 1 are mutually connected; therefore, both $a_{0,1}$ and $a_{1, 0}$ equal 1, and in general, $A = A^T$.

Given this representation of the graph, we can count triangles using linear algebra in the following way:

First, let $A \cdot B$ denote matrix multiplication. That is, $C = A \cdot B$ means $c_{i,j} = \sum_k a_{i,k} b_{k, j}$.

Next, let $A \odot B$ denote _elementwise_ multiplication. That is, $E = A \odot B$ means $e_{i, j} = a_{i, j} b_{i, j}$.

Then, here is a two-step method to compute the number of triangles, which we'll denote as $t(A)$:

$$
\begin{eqnarray}
       C & = & (A \cdot A) \odot A \\
    t(A) & = & \frac{1}{6} \sum_{i, j} c_{i,j}.
\end{eqnarray}
$$

The first step computes a "count" matrix $C$. Each element, $c_{i,j}$, counts the number of triangles in which both $i$ and $j$ appear.


 ## 2. Finding cosine similarity with regular additions in the data.
 The implementation of this problem as been done in the `Cosine_Simliarty_Numpy.ipynb` file.
 
 Cosine similarity is a metric, helpful in determining, how similar the data objects are irrespective of their size.
 Cosine similarity measures the cosine of the angle between two vectors projected in a multi-dimensional space.
 
 The formula to find the cosine similarity between two vectors is –
 
 $$ \begin{eqnarray} cos(x, y) & = & \frac{x \cdot y}{||x|| * ||y||} \end{eqnarray} $$
 
 Here we compute the cosine similarity by firstly finding the cosine simiarity between two given data arrays and then we add the second array to the stack of the first array so next time we can calculate the similarity using the entire previous data and the new data array in iteration.
