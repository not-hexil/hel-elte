### 1. Vector-Matrix Multiplication
Given $`A \in \mathbb{R}^{m \times n}`$ with columns $`\mathbf{a}_1, \dots, \mathbf{a}_n \in \mathbb{R}^m`$ and $`\mathbf{x} = (x_1, \dots, x_n)^T \in \mathbb{R}^n`$:

$$A\mathbf{x} = x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \dots + x_n\mathbf{a}_n \in \mathbb{R}^m$$

**Example:** Let $`A`$ and $`\mathbf{x}`$ be:

$$A = \begin{pmatrix} 1 & 2 \cr 3 & 0 \cr -1 & 4 \end{pmatrix}, \quad \mathbf{x} = \begin{pmatrix} 2 \cr -1 \end{pmatrix}$$

$$A\mathbf{x} = 2\begin{pmatrix} 1 \cr 3 \cr -1 \end{pmatrix} + (-1)\begin{pmatrix} 2 \cr 0 \cr 4 \end{pmatrix} = \begin{pmatrix} 2 - 2 \cr 6 - 0 \cr -2 - 4 \end{pmatrix} = \begin{pmatrix} 0 \cr 6 \cr -6 \end{pmatrix}$$

*(Row-Vector Multiplication: $`\mathbf{y}^T A = y_1\mathbf{r}_1 + \dots + y_m\mathbf{r}_m`$ where $`\mathbf{r}_i`$ are rows of $`A`$. With $`\mathbf{y}^T = (1, 0, 2)`$, $`\mathbf{y}^T A = 1(1, 2) + 0(3, 0) + 2(-1, 4) = (-1, 10)`$.)*

---

### 2. Checking if a Subset $`W \subseteq \mathbb{R}^n`$ is a Subspace
A subset $`W`$ is a subspace iff:

**(i)** $`\mathbf{0} \in W`$

**(ii)** $`\mathbf{u}, \mathbf{v} \in W \implies \mathbf{u} + \mathbf{v} \in W`$

**(iii)** $`\mathbf{u} \in W, c \in \mathbb{R} \implies c\mathbf{u} \in W`$

**$`\mathbb{R}^2`$ Example (Subspace):** $`W = \{(x, y) \in \mathbb{R}^2 \mid 2x - y = 0\}`$

**(i)** $`\mathbf{0} = \begin{pmatrix} 0 \cr 0 \end{pmatrix} \implies 2(0) - 0 = 0 \implies \mathbf{0} \in W`$

**(ii)** $`\mathbf{u} = \begin{pmatrix} x_1 \cr y_1 \end{pmatrix}, \mathbf{v} = \begin{pmatrix} x_2 \cr y_2 \end{pmatrix} \in W \implies 2(x_1+x_2) - (y_1+y_2) = (2x_1-y_1) + (2x_2-y_2) = 0 \implies \mathbf{u}+\mathbf{v} \in W`$

**(iii)** $`c \in \mathbb{R}, \mathbf{u} \in W \implies 2(cx) - (cy) = c(2x - y) = 0 \implies c\mathbf{u} \in W`$

**$`\mathbb{R}^3`$ Example (Not a Subspace):** $`W = \{(x, y, z) \in \mathbb{R}^3 \mid x + y + z = 1\}`$

Fails **(i)**: $`\mathbf{0} = \begin{pmatrix} 0 \cr 0 \cr 0 \end{pmatrix} \implies 0 + 0 + 0 = 0 \neq 1 \implies \mathbf{0} \notin W`$.

---

### 3. Whether $`\mathbf{y} \in \text{span}(\mathbf{u}, \mathbf{v})`$
$`\mathbf{y} \in \text{span}(\mathbf{u}, \mathbf{v}) \iff \exists c_1, c_2 \in \mathbb{R}`$ such that:

$$c_1\mathbf{u} + c_2\mathbf{v} = \mathbf{y}$$

**Example:** Let:

$$\mathbf{u} = \begin{pmatrix} 1 \cr 2 \cr 0 \end{pmatrix}, \quad \mathbf{v} = \begin{pmatrix} 0 \cr 1 \cr 3 \end{pmatrix}, \quad \mathbf{y} = \begin{pmatrix} 2 \cr 5 \cr 3 \end{pmatrix}$$

Set up the linear combination:

$$c_1\begin{pmatrix} 1 \cr 2 \cr 0 \end{pmatrix} + c_2\begin{pmatrix} 0 \cr 1 \cr 3 \end{pmatrix} = \begin{pmatrix} 2 \cr 5 \cr 3 \end{pmatrix}$$

This yields the system of equations:

$$1c_1 + 0c_2 = 2$$

$$2c_1 + 1c_2 = 5$$

$$0c_1 + 3c_2 = 3$$

Row-reduce the system matrix:

$$\begin{pmatrix} 1 & 0 & \vert & 2 \cr 2 & 1 & \vert & 5 \cr 0 & 3 & \vert & 3 \end{pmatrix} \stackrel{R_2 - 2R_1}{\longrightarrow} \begin{pmatrix} 1 & 0 & \vert & 2 \cr 0 & 1 & \vert & 1 \cr 0 & 3 & \vert & 3 \end{pmatrix} \stackrel{R_3 - 3R_2}{\longrightarrow} \begin{pmatrix} 1 & 0 & \vert & 2 \cr 0 & 1 & \vert & 1 \cr 0 & 0 & \vert & 0 \end{pmatrix}$$

The system is consistent ($`c_1 = 2, c_2 = 1 \implies 2\mathbf{u} + 1\mathbf{v} = \mathbf{y}`$), so $`\mathbf{y} \in \text{span}(\mathbf{u}, \mathbf{v})`$.

---

### 4. Finite Generator System of a Subspace
**Definition:** A finite set $`S = \{\mathbf{v}_1, \dots, \mathbf{v}_k\} \subset W`$ is a generator system of $`W`$ if $`\text{span}(S) = W`$.

**Example:** Determine a generator system of:

$$W = \{(2x-y+z, \ y+3z, \ x+y-2z, \ x-y) \in \mathbb{R}^4 \mid x, y, z \in \mathbb{R}, \ x+2y+z = 0\}$$

**Step 1:** Solve constraint for $`x`$: $`x = -2y - z`$.

**Step 2:** Substitute into the general vector:

$$\begin{pmatrix} 2(-2y-z) - y + z \cr y + 3z \cr (-2y-z) + y - 2z \cr (-2y-z) - y \end{pmatrix} = \begin{pmatrix} -5y - z \cr y + 3z \cr -y - 3z \cr -3y - z \end{pmatrix}$$

**Step 3:** Factor out free parameters $`y, z`$:

$$= y\begin{pmatrix} -5 \cr 1 \cr -1 \cr -3 \end{pmatrix} + z\begin{pmatrix} -1 \cr 3 \cr -3 \cr -1 \end{pmatrix}$$

**Generator System:**

$$S = { \begin{pmatrix} -5 \cr 1 \cr -1 \cr -3 \end{pmatrix}, \ \begin{pmatrix} -1 \cr 3 \cr -3 \cr -1 \end{pmatrix}}$$

---

### 5. Checking if $`\mathbf{w}`$ is Contained in Subspace $`W`$

**Case A ($`W`$ defined by equations):** Let $`W = \{(x, y, z) \in \mathbb{R}^3 \mid x - y + 2z = 0\}`$ and:

$$\mathbf{w} = \begin{pmatrix} 3 \cr 1 \cr -1 \end{pmatrix}$$

Substitute $`\mathbf{w}`$ into the equation: $`3 - 1 + 2(-1) = 0`$. True $`\implies \mathbf{w} \in W`$.

**Case B ($`W = \text{span}(\mathbf{v}_1, \mathbf{v}_2)`$):** Let:

$$\mathbf{v}_1 = \begin{pmatrix} 1 \cr 0 \cr 2 \end{pmatrix}, \quad \mathbf{v}_2 = \begin{pmatrix} 0 \cr 1 \cr 1 \end{pmatrix}, \quad \mathbf{w} = \begin{pmatrix} 1 \cr 2 \cr 5 \end{pmatrix}$$

Test if $`\mathbf{w}`$ is a linear combination of the spanning vectors:

$$c_1\mathbf{v}_1 + c_2\mathbf{v}_2 = \mathbf{w}$$

$$c_1\begin{pmatrix} 1 \cr 0 \cr 2 \end{pmatrix} + c_2\begin{pmatrix} 0 \cr 1 \cr 1 \end{pmatrix} = \begin{pmatrix} 1 \cr 2 \cr 5 \end{pmatrix}$$

Expand each coordinate to get the system of equations:

$$\begin{cases} 1c_1 + 0c_2 = 1 \cr 0c_1 + 1c_2 = 2 \cr 2c_1 + 1c_2 = 5 \end{cases}$$

From the first two equations, we already know $`c_1 = 1`$ and $`c_2 = 2`$. Plugging those into the third equation gives $`2(1) + 1(2) = 4 \neq 5`$, which is a contradiction.

Row-reduce the system matrix step by step to see it formally:

$$\begin{pmatrix} 1 & 0 & \vert & 1 \cr 0 & 1 & \vert & 2 \cr 2 & 1 & \vert & 5 \end{pmatrix} \stackrel{R_3 - 2R_1}{\longrightarrow} \begin{pmatrix} 1 & 0 & \vert & 1 \cr 0 & 1 & \vert & 2 \cr 0 & 1 & \vert & 3 \end{pmatrix} \stackrel{R_3 - R_2}{\longrightarrow} \begin{pmatrix} 1 & 0 & \vert & 1 \cr 0 & 1 & \vert & 2 \cr 0 & 0 & \vert & 1 \end{pmatrix}$$

The third row of the final matrix means $`0c_1 + 0c_2 = 1`$, i.e., $`0 = 1`$ (inconsistent). No scalars $`c_1, c_2`$ exist, so $`\mathbf{w} \notin W`$.
