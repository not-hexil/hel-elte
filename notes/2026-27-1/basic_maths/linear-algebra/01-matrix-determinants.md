# Matrices and Determinants

## Matrix Product
![matrix product](../../../../assets/matrix_product.webp)

Given two matrices $A$ of dimensions $m \times n$ and $B$ of dimensions $n \times p$, their product $P = AB$ is a matrix of dimensions $m \times p$:

$$
P = \begin{bmatrix}
c_{11} & c_{12} & \cdots & c_{1p} \\
c_{21} & c_{22} & \cdots & c_{2p} \\
\vdots & \vdots & \ddots & \vdots \\
c_{m1} & c_{m2} & \cdots & c_{mp}
\end{bmatrix}
$$

Each entry $c_{ij}$ is the dot product of the **$i$-th row of $A$** and the **$j$-th column of $B$**:

$$
c_{ij} = \sum_{k=1}^{n} a_{ik} b_{kj} = a_{i1}b_{1j} + a_{i2}b_{2j} + \dots + a_{in}b_{nj}
$$

#### Example (from the diagram)
For the highlighted top-left element ($i = 1, j = 1$) in a $3 \times 3$ multiplication ($n = 3$):

$$
c_{11} = a_{11}b_{11} + a_{12}b_{21} + a_{13}b_{31}
$$
