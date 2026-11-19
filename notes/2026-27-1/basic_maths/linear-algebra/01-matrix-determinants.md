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

**Explaining the provided diagram**:
For the highlighted top-left element ($i = 1, j = 1$) in a $3 \times 3$ multiplication ($n = 3$):

$$
c_{11} = a_{11}b_{11} + a_{12}b_{21} + a_{13}b_{31}
$$

## Inverse of a Matrix

### Cofactor Method
![cofactor method](../../../../assets/matrix_inverse_one.webp)

Given an arbitrary $3 \times 3$ square matrix $A$:

$$
A = \begin{bmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{bmatrix}
$$

The inverse $A^{-1}$ exists if and only if the determinant $\det(A) \neq 0$, and is defined as the **adjugate** (transpose of the cofactor matrix) divided by the **determinant**:

$$
A^{-1} = \frac{1}{\det(A)} \text{adj}(A) = \frac{1}{\det(A)} C^T
$$

---

#### 1. Determinant of $A$
Expand along the first row to compute $\det(A)$:

$$
\det(A) = a_{11}(a_{22}a_{33} - a_{23}a_{32}) - a_{12}(a_{21}a_{33} - a_{23}a_{31}) + a_{13}(a_{21}a_{32} - a_{22}a_{31})
$$

---

#### 2. Matrix of Minors and Cofactors ($C$)
For each entry $a_{ij}$, its **minor** $M_{ij}$ is the determinant of the $2 \times 2$ submatrix formed by removing row $i$ and column $j$. Each **cofactor** $C_{ij}$ applies a checkerboard sign pattern:

$$
C_{ij} = (-1)^{i+j} M_{ij}
$$

Assembling all nine cofactors gives the **cofactor matrix** $C$:

$$
C = \begin{bmatrix}
+(a_{22}a_{33} - a_{23}a_{32}) & -(a_{21}a_{33} - a_{23}a_{31}) & +(a_{21}a_{32} - a_{22}a_{31}) \\
-(a_{12}a_{33} - a_{13}a_{32}) & +(a_{11}a_{33} - a_{13}a_{31}) & -(a_{11}a_{32} - a_{12}a_{31}) \\
+(a_{12}a_{23} - a_{13}a_{22}) & -(a_{11}a_{23} - a_{13}a_{21}) & +(a_{11}a_{22} - a_{12}a_{21})
\end{bmatrix}
$$

---

#### 3. Adjugate Matrix $\text{adj}(A)$
Take the **transpose** of the cofactor matrix ($C^T$, swapping rows and columns) to get the adjugate matrix:

$$
\text{adj}(A) = C^T = \begin{bmatrix}
C_{11} & C_{21} & C_{31} \\
C_{12} & C_{22} & C_{32} \\
C_{13} & C_{23} & C_{33}
\end{bmatrix}
$$

---

#### 4. Final Inverse ($A^{-1}$)
Divide every entry of $\text{adj}(A)$ by $\det(A)$:

$$
A^{-1} = \frac{1}{\det(A)} \begin{bmatrix}
C_{11} & C_{21} & C_{31} \\
C_{12} & C_{22} & C_{32} \\
C_{13} & C_{23} & C_{33}
\end{bmatrix}
$$

### Gauss–Jordan Elimination Method
![matrix product](../../../../assets/matrix_inverse_two.webp)
You can select **any convenient nonzero entry** as your pivot (such as an existing $1$ or $-1$ to avoid fractions).

When choosing pivots out of diagonal order, you eliminate all other entries in the pivot's column, then perform **row swaps** at the end so the left side becomes the ordered identity matrix $I$:

$$
[A \mid I] \rightarrow [P \mid B] \rightarrow [I \mid A^{-1}]
$$

---

#### Sample Matrix
Consider a $3 \times 3$ matrix $A$ where the top-left entry is $0$ (forcing us to choose a different pivot):

$$
A = \begin{bmatrix}
0 & 2 & 1 \\
1 & -2 & -3 \\
-1 & 1 & 2
\end{bmatrix}
$$

Set up the augmented matrix $[A \mid I]$:

$$
\begin{bmatrix}
0 & 2 & 1 & | & 1 & 0 & 0 \\
1 & -2 & -3 & | & 0 & 1 & 0 \\
-1 & 1 & 2 & | & 0 & 0 & 1
\end{bmatrix}
$$

---

#### 1. Pick Pivot 1: Entry $(2, 1) = 1$
Rather than swapping rows immediately, select the $1$ in **Row 2, Column 1** as the pivot and zero out the rest of Column 1 ($R_3 \leftarrow R_3 + R_2$):

$$
\begin{bmatrix}
0 & 2 & 1 & | & 1 & 0 & 0 \\
\mathbf{1} & -2 & -3 & | & 0 & 1 & 0 \\
0 & -1 & -1 & | & 0 & 1 & 1
\end{bmatrix}
$$

---

#### 2. Pick Pivot 2: Entry $(3, 2) = -1$
Instead of dividing Row 1 by $2$, select the $-1$ in **Row 3, Column 2** as the next pivot. Scale it to $+1$ ($R_3 \leftarrow -R_3$):

$$
\begin{bmatrix}
0 & 2 & 1 & | & 1 & 0 & 0 \\
1 & -2 & -3 & | & 0 & 1 & 0 \\
0 & \mathbf{1} & 1 & | & 0 & -1 & -1
\end{bmatrix}
$$

Eliminate the remaining entries in Column 2 ($R_1 \leftarrow R_1 - 2R_3$ and $R_2 \leftarrow R_2 + 2R_3$):

$$
\begin{bmatrix}
0 & 0 & -1 & | & 1 & 2 & 2 \\
1 & 0 & -1 & | & 0 & -1 & -2 \\
0 & 1 & 1 & | & 0 & -1 & -1
\end{bmatrix}
$$

---

#### 3. Pick Pivot 3: Entry $(1, 3) = -1$
Select the $-1$ in **Row 1, Column 3** as the final pivot. Scale it to $+1$ ($R_1 \leftarrow -R_1$):

$$
\begin{bmatrix}
0 & 0 & \mathbf{1} & | & -1 & -2 & -2 \\
1 & 0 & -1 & | & 0 & -1 & -2 \\
0 & 1 & 1 & | & 0 & -1 & -1
\end{bmatrix}
$$

Eliminate the remaining entries in Column 3 ($R_2 \leftarrow R_2 + R_1$ and $R_3 \leftarrow R_3 - R_1$):

$$
\begin{bmatrix}
0 & 0 & 1 & | & -1 & -2 & -2 \\
1 & 0 & 0 & | & -1 & -3 & -4 \\
0 & 1 & 0 & | & 1 & 1 & 1
\end{bmatrix}
$$

---

#### 4. Reorder Rows to Form $I$
The left side is now a shuffled identity matrix. Reorder the rows ($R_1 \leftrightarrow R_2$, then $R_2 \leftrightarrow R_3$) so the pivots sit along the main diagonal:

$$
\begin{bmatrix}
1 & 0 & 0 & | & -1 & -3 & -4 \\
0 & 1 & 0 & | & 1 & 1 & 1 \\
0 & 0 & 1 & | & -1 & -2 & -2
\end{bmatrix}
$$

---

#### 5. Final Inverse ($A^{-1}$)

$$
A^{-1} = \begin{bmatrix}
-1 & -3 & -4 \\
1 & 1 & 1 \\
-1 & -2 & -2
\end{bmatrix}
$$

## Matrix, Transpose, Inverse, and Determinant Laws

Assume matrices $A, B, C$ have compatible dimensions for each operation, $I$ is the identity matrix, $0$ is the zero matrix, and $c, k$ are scalars.

---

#### 1. Matrix Addition & Scalar Multiplication
* **Commutative Law:** $A + B = B + A$
* **Associative Law (Addition):** $(A + B) + C = A + (B + C)$
* **Additive Identity:** $A + 0 = A$
* **Additive Inverse:** $A + (-A) = 0$
* **Scalar Distributive Laws:**
  * $c(A + B) = cA + cB$
  * $(c + k)A = cA + kA$
* **Scalar Associative Law:** $(ck)A = c(kA)$

---

#### 2. Matrix Multiplication
* **Associative Law:** $(AB)C = A(BC)$
* **Left Distributive Law:** $A(B + C) = AB + AC$
* **Right Distributive Law:** $(A + B)C = AC + BC$
* **Multiplicative Identity:** $AI = IA = A$
* **Zero Property:** $A0 = 0$ and $0A = 0$
* **Scalar Compatibility:** $c(AB) = (cA)B = A(cB)$
* **Non-Commutativity (Important):** In general, $AB \neq BA$.
* **Zero Divisors (Important):** $AB = 0$ does **not** imply $A = 0$ or $B = 0$.
* **No Cancellation Law:** $AB = AC$ does **not** imply $B = C$ (unless $A$ is invertible).

---

#### 3. Transpose Laws ($A^T$)
* **Involution (Double Transpose):** $(A^T)^T = A$
* **Addition / Subtraction:** $(A \pm B)^T = A^T \pm B^T$
* **Scalar Multiplication:** $(cA)^T = cA^T$
* **Product Reversal Rule:** $(AB)^T = B^T A^T$
* **Symmetric Matrix:** $A$ is symmetric if $A^T = A$.
* **Skew-Symmetric Matrix:** $A$ is skew-symmetric if $A^T = -A$.

---

#### 4. Inverse Laws ($A^{-1}$)
For invertible / non-singular $n \times n$ matrices where $\det(A) \neq 0$

* **Definition:** $AA^{-1} = A^{-1}A = I$
* **Double Inverse:** $(A^{-1})^{-1} = A$
* **Product Reversal Rule:** $(AB)^{-1} = B^{-1}A^{-1}$
* **Transpose Commutativity:** $(A^T)^{-1} = (A^{-1})^T$
* **Scalar Multiple:** $(cA)^{-1} = \frac{1}{c}A^{-1}$ (for $c \neq 0$)
* **Power Rule:** $(A^k)^{-1} = (A^{-1})^k = A^{-k}$
* **Adjugate Identity:** $A \cdot \text{adj}(A) = \text{adj}(A) \cdot A = \det(A)I$

---

#### 5. Determinant Laws ($\det(A)$ or $|A|$)
For $n \times n$ square matrices

* **Identity & Zero Matrices:** $\det(I) = 1$ and $\det(0) = 0$
* **Transpose Invariance:** $\det(A^T) = \det(A)$
* **Product Rule:** $\det(AB) = \det(A)\det(B)$
* **Inverse Rule:** $\det(A^{-1}) = \frac{1}{\det(A)}$
* **Power Rule:** $\det(A^k) = (\det(A))^k$
* **Scalar Multiplication Rule:** $\det(cA) = c^n \det(A)$ (each of the $n$ rows is scaled by $c$)
* **Triangular & Diagonal Matrices:** If $A$ is upper triangular, lower triangular, or diagonal, $\det(A)$ is the product of its main diagonal entries:
  $$\det(A) = a_{11}a_{22}\cdots a_{nn}$$
* **Non-Additivity (Important):** In general, $\det(A + B) \neq \det(A) + \det(B)$.

---

#### 6. Elementary Row Operation Effects on Determinants
* **Swapping two rows ($R_i \leftrightarrow R_j$):** Multiplies the determinant by $-1$.
* **Multiplying a row by a scalar ($R_i \leftarrow cR_i$):** Multiplies the determinant by $c$.
* **Adding a multiple of one row to another ($R_i \leftarrow R_i + cR_j$):** Leaves the determinant **unchanged**.
* **Zero / Duplicate Rows:** If a matrix has a row (or column) of all zeros, or two identical/proportional rows (or columns), then $\det(A) = 0$.

---

#### 7. Trace Identities
The sum of the main diagonal entries: $\text{tr}(A) = \sum_{i=1}^{n} a_{ii}$

* **Linearity:** $\text{tr}(A + B) = \text{tr}(A) + \text{tr}(B)$ and $\text{tr}(cA) = c\,\text{tr}(A)$
* **Transpose Invariance:** $\text{tr}(A^T) = \text{tr}(A)$
* **Cyclic Property:** $\text{tr}(AB) = \text{tr}(BA)$ and $\text{tr}(ABC) = \text{tr}(BCA) = \text{tr}(CAB)$
