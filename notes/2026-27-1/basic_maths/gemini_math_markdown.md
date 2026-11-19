# Markdown Mathematical Expressions Cheatsheet

In Markdown (specifically implementations supporting MathJax or KaTeX, such as GitHub, Notion, Jupyter, and Obsidian), mathematical expressions are written using **LaTeX** syntax.

* **Inline Math:** Enclose expressions in single dollar signs: `$ ... $`
* **Block (Display) Math:** Enclose expressions in double dollar signs on their own lines:
  ```markdown
  $$
  ...
  $$
  ```

---

## 1. Basic Arithmetic & Algebra

| Concept | Rendered Preview | Markdown / LaTeX Syntax |
| :--- | :---: | :--- |
| Addition & Subtraction | $a + b - c$ | `` `$a + b - c$` `` |
| Multiplication (Dot & Cross) | $a \cdot b \times c$ | `` `$a \cdot b \times c$` `` |
| Division (Slash & Fraction) | $a / b \quad \text{or} \quad \frac{a}{b}$ | `` `$a / b$` `` or `` `$\frac{a}{b}$` `` |
| Display Fraction (Larger) | $\dfrac{a + b}{c + d}$ | `` `$\dfrac{a + b}{c + d}$` `` |
| Exponents / Superscripts | $x^2, \quad e^{i\pi}$ | `` `$x^2$` ``, `` `$e^{i\pi}$` `` |
| Subscripts | $x_1, \quad a_{i,j}$ | `` `$x_1$` ``, `` `$a_{i,j}$` `` |
| Square Root & $n$-th Root | $\sqrt{x}, \quad \sqrt[n]{x}$ | `` `$\sqrt{x}$` ``, `` `$\sqrt[n]{x}$` `` |
| Plus-Minus & Minus-Plus | $\pm a, \quad \mp b$ | `` `$\pm a$` ``, `` `$\mp b$` `` |
| Absolute Value & Floor/Ceiling | $|x|, \quad \lfloor x \rfloor, \quad \lceil x \rceil$ | `` `$|x|$` ``, `` `$\lfloor x \rfloor$` ``, `` `$\lceil x \rceil$` `` |
| Modulo | $a \equiv b \pmod{m}$ | `` `$a \equiv b \pmod{m}$` `` |

---

## 2. Relational & Logical Operators

| Concept | Rendered Preview | Markdown / LaTeX Syntax |
| :--- | :---: | :--- |
| Inequalities | $<, \quad >, \quad \leq, \quad \geq, \quad \neq$ | `` `$<, >, \leq, \geq, \neq$` `` |
| Approximations | $\approx, \quad \sim, \quad \simeq, \quad \cong$ | `` `$\approx, \sim, \simeq, \cong$` `` |
| Proportional To | $y \propto x$ | `` `$y \propto x$` `` |
| Quantifiers (For all, Exists) | $\forall x, \quad \exists y, \quad \nexists z$ | `` `$\forall x, \exists y, \nexists z$` `` |
| Logical Connectives | $\land \text{ (and)}, \quad \lor \text{ (or)}, \quad \neg \text{ (not)}$ | `` `$\land, \lor, \neg$` `` |
| Implications & Equivalence | $\implies, \quad \impliedby, \quad \iff$ | `` `$\implies, \impliedby, \iff$` `` |
| Therefore & Because | $\therefore, \quad \because$ | `` `$\therefore, \because$` `` |

---

## 3. Sets & Number Systems

| Concept | Rendered Preview | Markdown / LaTeX Syntax |
| :--- | :---: | :--- |
| Number Sets | $\mathbb{N}, \quad \mathbb{Z}, \quad \mathbb{Q}, \quad \mathbb{R}, \quad \mathbb{C}$ | `` `$\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R}, \mathbb{C}$` `` |
| Element Of / Not Element Of | $x \in A, \quad y \notin A$ | `` `$x \in A, y \notin A$` `` |
| Subsets | $A \subset B, \quad A \subseteq B, \quad A \nsubseteq B$ | `` `$A \subset B, A \subseteq B, A \nsubseteq B$` `` |
| Union & Intersection | $A \cup B, \quad A \cap B$ | `` `$A \cup B, A \cap B$` `` |
| Set Difference & Empty Set | $A \setminus B, \quad \emptyset \text{ or } \varnothing$ | `` `$A \setminus B, \emptyset, \varnothing$` `` |
| Set Builder Notation | $\{x \in \mathbb{R} \mid x > 0\}$ | `` `$\{x \in \mathbb{R} \mid x > 0\}$` `` |

---

## 4. Pre-Calculus & Trigonometry

| Concept | Rendered Preview | Markdown / LaTeX Syntax |
| :--- | :---: | :--- |
| Trig Functions | $\sin\theta, \quad \cos\theta, \quad \tan\theta$ | `` `$\sin\theta, \cos\theta, \tan\theta$` `` |
| Inverse Trig | $\arcsin x, \quad \cos^{-1} x$ | `` `$\arcsin x, \cos^{-1} x$` `` |
| Hyperbolic Functions | $\sinh x, \quad \cosh x, \quad \tanh x$ | `` `$\sinh x, \cosh x, \tanh x$` `` |
| Logarithms | $\log x, \quad \log_b x, \quad \ln x$ | `` `$\log x, \log_b x, \ln x$` `` |
| Function Composition | $(f \circ g)(x) = f(g(x))$ | `` `$(f \circ g)(x) = f(g(x))$` `` |
| Combinatorics (Binomial) | $\binom{n}{k} = \frac{n!}{k!(n-k)!}$ | `` `$\binom{n}{k} = \frac{n!}{k!(n-k)!}$` `` |
| Degrees & Angles | $90^\circ, \quad \angle ABC$ | `` `$90^\circ, \angle ABC$` `` |

### Piecewise Functions
**Preview:**
$$
f(x) = \begin{cases} 
x^2 & \text{if } x \geq 0 \\
-x & \text{if } x < 0 
\end{cases}
$$

**Syntax:**
```latex
$$
f(x) = \begin{cases} 
x^2 & \text{if } x \geq 0 \\
-x & \text{if } x < 0 
\end{cases}
$$
```

---

## 5. Calculus & Analysis

| Concept | Rendered Preview | Markdown / LaTeX Syntax |
| :--- | :---: | :--- |
| Limits | $\lim_{x \to \infty} f(x), \quad \lim_{x \to 0^+} f(x)$ | `` `$\lim_{x \to \infty} f(x)$` ``, `` `$\lim_{x \to 0^+} f(x)$` `` |
| Derivatives (Prime & Leibniz) | $f'(x), \quad f''(x), \quad \frac{dy}{dx}, \quad \frac{d^2y}{dx^2}$ | `` `$f'(x), f''(x), \frac{dy}{dx}, \frac{d^2y}{dx^2}$` `` |
| Partial Derivatives | $\frac{\partial f}{\partial x}, \quad \frac{\partial^2 f}{\partial x \partial y}$ | `` `$\frac{\partial f}{\partial x}, \frac{\partial^2 f}{\partial x \partial y}$` `` |
| Indefinite & Definite Integrals | $\int f(x)\,dx, \quad \int_{a}^{b} f(x)\,dx$ | `` `$\int f(x)\,dx, \int_{a}^{b} f(x)\,dx$` `` |
| Multiple & Contour Integrals | $\iint_D, \quad \iiint_V, \quad \oint_C$ | `` `$\iint_D, \iiint_V, \oint_C$` `` |
| Evaluation Bar | $\left. F(x) \right|_a^b = F(b) - F(a)$ | `` `$\left. F(x) \right\|_a^b = F(b) - F(a)$` `` |
| Summation & Product | $\sum_{i=1}^{n} i^2, \quad \prod_{i=1}^{n} x_i$ | `` `$\sum_{i=1}^{n} i^2, \prod_{i=1}^{n} x_i$` `` |
| Vector Calculus (Del / Nabla) | $\nabla f, \quad \nabla \cdot \mathbf{F}, \quad \nabla \times \mathbf{F}, \quad \Delta f$ | `` `$\nabla f, \nabla \cdot \mathbf{F}, \nabla \times \mathbf{F}, \Delta f$` `` |

---

## 6. Linear Algebra & Matrices

### Vectors & Norms
| Concept | Rendered Preview | Markdown / LaTeX Syntax |
| :--- | :---: | :--- |
| Vector Notations | $\vec{v}, \quad \mathbf{v}, \quad \hat{u} \text{ (unit vector)}$ | `` `$\vec{v}, \mathbf{v}, \hat{u}$` `` |
| Dot & Cross Product | $\mathbf{u} \cdot \mathbf{v}, \quad \mathbf{u} \times \mathbf{v}$ | `` `$\mathbf{u} \cdot \mathbf{v}, \mathbf{u} \times \mathbf{v}$` `` |
| Inner Product & Norm | $\langle \mathbf{u}, \mathbf{v} \rangle, \quad \|\mathbf{v}\|, \quad \|\mathbf{v}\|_2$ | `` `$\langle \mathbf{u}, \mathbf{v} \rangle, \|\mathbf{v}\|, \|\mathbf{v}\|_2$` `` |
| Matrix Operations | $A^T, \quad A^{-1}, \quad A^\dagger, \quad \det(A), \quad \operatorname{tr}(A)$ | `` `$A^T, A^{-1}, A^\dagger, \det(A), \operatorname{tr}(A)$` `` |
| Tensor / Kronecker Product | $A \otimes B, \quad V \oplus W$ | `` `$A \otimes B, V \oplus W$` `` |

### Matrix Environments
Use `&` to separate columns and `\\` to start a new row.

| Matrix Type | Rendered Preview | Markdown / LaTeX Syntax |
| :--- | :---: | :--- |
| **Parentheses** (`pmatrix`) | $\begin{pmatrix} a & b \\ c & d \end{pmatrix}$ | `` `$\begin{pmatrix} a & b \\ c & d \end{pmatrix}$` `` |
| **Brackets** (`bmatrix`) | $\begin{bmatrix} a & b \\ c & d \end{bmatrix}$ | `` `$\begin{bmatrix} a & b \\ c & d \end{bmatrix}$` `` |
| **Determinant** (`vmatrix`) | $\begin{vmatrix} a & b \\ c & d \end{vmatrix}$ | `` `$\begin{vmatrix} a & b \\ c & d \end{vmatrix}$` `` |
| **Norm** (`Vmatrix`) | $\begin{Vmatrix} a & b \\ c & d \end{Vmatrix}$ | `` `$\begin{Vmatrix} a & b \\ c & d \end{Vmatrix}$` `` |
| **Braces** (`Bmatrix`) | $\begin{Bmatrix} a & b \\ c & d \end{Bmatrix}$ | `` `$\begin{Bmatrix} a & b \\ c & d \end{Bmatrix}$` `` |

### Advanced Matrix Formatting (Ellipses & Augmented Matrices)
**Preview:**
$$
A_{m,n} = \begin{bmatrix}
a_{1,1} & a_{1,2} & \cdots & a_{1,n} \\
a_{2,1} & a_{2,2} & \cdots & a_{2,n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{m,1} & a_{m,2} & \cdots & a_{m,n} 
\end{bmatrix}
\qquad
\left[\begin{array}{cc|c}
1 & 2 & 3 \\
4 & 5 & 6
\end{array}\right]
$$

**Syntax:**
```latex
$$
A_{m,n} = \begin{bmatrix}
a_{1,1} & a_{1,2} & \cdots & a_{1,n} \\
a_{2,1} & a_{2,2} & \cdots & a_{2,n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{m,1} & a_{m,2} & \cdots & a_{m,n} 
\end{bmatrix}
\qquad
\left[\begin{array}{cc|c}
1 & 2 & 3 \\
4 & 5 & 6
\end{array}\right]
$$
```

---

## 7. Multi-Line Equation Alignment

Use the `aligned` environment with `&` to align equations at the equals sign.

**Preview:**
$$
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \mathbf{B} &= 0 \\
\nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\
\nabla \times \mathbf{B} &= \mu_0\mathbf{J} + \mu_0\varepsilon_0\frac{\partial \mathbf{E}}{\partial t}
\end{aligned}
$$

**Syntax:**
```latex
$$
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \mathbf{B} &= 0 \\
\nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\
\nabla \times \mathbf{B} &= \mu_0\mathbf{J} + \mu_0\varepsilon_0\frac{\partial \mathbf{E}}{\partial t}
\end{aligned}
$$
```

---

## 8. Greek Alphabet Reference

| Letter | Lowercase | Uppercase | Syntax (Lower / Upper) |
| :--- | :---: | :---: | :--- |
| Alpha | $\alpha$ | $A$ | `` `\alpha` `` / `` `A` `` |
| Beta | $\beta$ | $B$ | `` `\beta` `` / `` `B` `` |
| Gamma | $\gamma$ | $\Gamma$ | `` `\gamma` `` / `` `\Gamma` `` |
| Delta | $\delta$ | $\Delta$ | `` `\delta` `` / `` `\Delta` `` |
| Epsilon | $\epsilon, \varepsilon$ | $E$ | `` `\epsilon, \varepsilon` `` / `` `E` `` |
| Zeta | $\zeta$ | $Z$ | `` `\zeta` `` / `` `Z` `` |
| Eta | $\eta$ | $H$ | `` `\eta` `` / `` `H` `` |
| Theta | $\theta, \vartheta$ | $\Theta$ | `` `\theta, \vartheta` `` / `` `\Theta` `` |
| Kappa | $\kappa$ | $K$ | `` `\kappa` `` / `` `K` `` |
| Lambda | $\lambda$ | $\Lambda$ | `` `\lambda` `` / `` `\Lambda` `` |
| Mu | $\mu$ | $M$ | `` `\mu` `` / `` `M` `` |
| Nu | $\nu$ | $N$ | `` `\nu` `` / `` `N` `` |
| Xi | $\xi$ | $\Xi$ | `` `\xi` `` / `` `\Xi` `` |
| Pi | $\pi, \varpi$ | $\Pi$ | `` `\pi, \varpi` `` / `` `\Pi` `` |
| Rho | $\rho, \varrho$ | $P$ | `` `\rho, \varrho` `` / `` `P` `` |
| Sigma | $\sigma, \varsigma$ | $\Sigma$ | `` `\sigma, \varsigma` `` / `` `\Sigma` `` |
| Tau | $\tau$ | $T$ | `` `\tau` `` / `` `T` `` |
| Phi | $\phi, \varphi$ | $\Phi$ | `` `\phi, \varphi` `` / `` `\Phi` `` |
| Chi | $\chi$ | $X$ | `` `\chi` `` / `` `X` `` |
| Psi | $\psi$ | $\Psi$ | `` `\psi` `` / `` `\Psi` `` |
| Omega | $\omega$ | $\Omega$ | `` `\omega` `` / `` `\Omega` `` |

---

## 9. Spacing, Brackets & Accents

| Concept | Rendered Preview | Markdown / LaTeX Syntax |
| :--- | :---: | :--- |
| Auto-Sizing Brackets | $\left( \frac{a}{b} \right), \quad \left[ \frac{a}{b} \right], \quad \left\{ \frac{a}{b} \right\}$ | `` `\left( \frac{a}{b} \right)` `` |
| Overbrace & Underbrace | $\overbrace{x + \cdots + x}^{n \text{ times}}, \quad \underbrace{a + b}_{c}$ | `` `\overbrace{...}^{...}, \underbrace{...}_{...}` `` |
| Accents | $\hat{x}, \quad \bar{x}, \quad \tilde{x}, \quad \dot{x}, \quad \ddot{x}$ | `` `\hat{x}, \bar{x}, \tilde{x}, \dot{x}, \ddot{x}` `` |
| Text Inside Math | $x = 5 \text{ if } y = 2$ | `` `$x = 5 \text{ if } y = 2$` `` |
| Manual Spacing | $a\,b \text{ (thin)}, \quad a\;b \text{ (thick)}, \quad a\quad b \text{ (quad)}$ | `` `\,` ``, `` `\;` ``, `` `\quad` ``, `` `\qquad` `` |