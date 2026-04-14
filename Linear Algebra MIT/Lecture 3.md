# Lecture 3 Matrices Multiplication and Inverses

## 1. Five ways of matrices multiplication

```math
\underbrace{
\begin{bmatrix}
a_{11} & a_{12} & \dots  & a_{1n} \\
a_{21} & a_{22} & \dots  & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots  & a_{mn}
\end{bmatrix}
}_{A_{m \times n}}
\underbrace{
\begin{bmatrix}
b_{11} & b_{12} & \dots  & b_{1p} \\
b_{21} & b_{22} & \dots  & b_{2p} \\
\vdots & \vdots & \ddots & \vdots \\
b_{n1} & b_{n2} & \dots  & b_{np}
\end{bmatrix}
}_{B_{n \times p}}
=
\underbrace{
\begin{bmatrix}
c_{11} & c_{12} & \dots  & c_{1p} \\
c_{21} & c_{22} & \dots  & c_{2p} \\
\vdots & \vdots & \ddots & \vdots \\
c_{m1} & c_{m2} & \dots  & c_{mp}
\end{bmatrix}
}_{C_{m \times p}}
```

### 1.1 Entry $C_{ij}$ is dot product of row $i$ of A and column $j$ of B
```math
\underbrace{
\begin{bmatrix}
a_{11} & a_{12} & \dots  & a_{1n} \\
\vdots & \vdots & \ddots & \vdots \\
\color{red}{a_{i1}} & \color{red}{a_{i2}} & \color{red}{\dots}  & \color{red}{a_{in}} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots  & a_{mn}
\end{bmatrix}
}_{A_{m \times n}}
\underbrace{
\begin{bmatrix}
b_{11} & \dots & \color{blue}{b_{1j}} & \dots & b_{1p} \\
b_{21} & \dots & \color{blue}{b_{2j}} & \dots & b_{2p} \\
\vdots & \ddots & \color{blue}{\vdots} & \ddots & \vdots \\
b_{n1} & \dots & \color{blue}{b_{nj}} & \dots & b_{np} 
\end{bmatrix}
}_{B_{n \times p}}
=
\underbrace{
\begin{bmatrix}
c_{11} & \dots & c_{1j} & \dots & c_{1p} \\
\vdots & \ddots & \vdots & \ddots & \vdots \\
c_{i1} & \dots & \color{purple}{c_{ij}} & \dots & c_{ip} \\
\vdots & \ddots & \vdots & \ddots & \vdots \\
c_{m1} & \dots & c_{mj} & \dots & c_{mp}
\end{bmatrix}
}_{C_{m \times p}}
```

$$c_{ij} = \sum_{k=1}^{n} \color{red}{a_{ik}} \color{blue}{b_{kj}} = \color{red}{a_{i1}}\color{blue}{b_{1j}} + \color{red}{a_{i2}}\color{blue}{b_{2j}} + \dots + \color{red}{a_{in}}\color{blue}{b_{nj}}$$

### 1.2 Columns of C are combinations of columns of A

```math
\underbrace{
\begin{bmatrix}
a_{11} & a_{12} & \dots  & a_{1n} \\
a_{21} & a_{22} & \dots  & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots  & a_{mn}
\end{bmatrix}
}_{A_{m \times n}}
\underbrace{
\begin{bmatrix}
\color{green}{b_{11}} & \dots & \color{blue}{b_{1j}} & \dots & \color{orange}{b_{1p}} \\
\color{green}{b_{21}} & \dots & \color{blue}{b_{2j}} & \dots & \color{orange}{b_{2p}} \\
\color{green}{\vdots} & \ddots & \color{blue}{\vdots} & \ddots & \color{orange}{\vdots} \\
\color{green}{b_{n1}} & \dots & \color{blue}{b_{nj}} & \dots & \color{orange}{b_{np}} 
\end{bmatrix}
}_{B_{n \times p}}
=
\underbrace{
\begin{bmatrix}
\color{green}{c_{11}} & \dots & \color{blue}{c_{1j}} & \dots & \color{orange}{c_{1p}} \\
\color{green}{c_{21}} & \dots & \color{blue}{c_{22}} & \dots & \color{orange}{c_{22}} \\
\color{green}{\vdots} & \ddots & \color{blue}{\vdots} & \ddots & \color{orange}{\vdots} \\
\color{green}{c_{m1}} & \dots & \color{blue}{c_{mj}} & \dots & \color{orange}{c_{mp}}
\end{bmatrix}
}_{C_{m \times p}}
```

$$\mathbf{c}_j = A \mathbf{b}_j = \sum_{k=1}^{n} b_{kj} \mathbf{a}_k = b_{1j}\mathbf{a}_1 + b_{2j}\mathbf{a}_2 + \dots + b_{nj}\mathbf{a}_n$$

### 1.3 Rows of C are combinations of rows of B
```math
\underbrace{
\begin{bmatrix}
\color{green}{a_{11}} & \color{green}{a_{12}} & \color{green}{\dots}  & \color{green}{a_{1n}} \\
\vdots & \vdots & \ddots & \vdots \\
\color{blue}{a_{i1}} & \color{blue}{a_{i2}} & \color{blue}{\dots}  & \color{blue}{a_{in}} \\
\vdots & \vdots & \ddots & \vdots \\
\color{orange}{a_{m1}} & \color{orange}{a_{m2}} & \color{orange}{\dots}  & \color{orange}{a_{mn}}
\end{bmatrix}
}_{A_{m \times n}}
\underbrace{
\begin{bmatrix}
b_{11} & b_{12} & \dots  & b_{1p} \\
b_{21} & b_{22} & \dots  & b_{2p} \\
\vdots & \vdots & \ddots & \vdots \\
b_{n1} & b_{n2} & \dots  & b_{np}
\end{bmatrix}
}_{B_{n \times p}}
=
\underbrace{
\begin{bmatrix}
\color{green}{c_{11}} & \color{green}{c_{12}} & \color{green}{\dots}  & \color{green}{c_{1p}} \\
\vdots & \vdots & \ddots & \vdots \\
\color{blue}{c_{i1}} & \color{blue}{c_{i2}} & \color{blue}{\dots}  & \color{blue}{c_{ip}} \\
\vdots & \vdots & \ddots & \vdots \\
\color{orange}{c_{m1}} & \color{orange}{c_{m2}} & \color{orange}{\dots}  & \color{orange}{c_{mp}}
\end{bmatrix}
}_{C_{m \times p}}
```

$$\mathbf{r}_i(C) = \mathbf{r}_i(A) B = \sum_{k=1}^{n} a_{ik} \mathbf{r}_k(B) = a_{i1}\mathbf{r}_1(B) + a_{i2}\mathbf{r}_2(B) + \dots + a_{in}\mathbf{r}_n(B)$$

### 1.4 AB is sum of outer product (columns of A) x (rows of B)

$$AB = \sum_{k=1}^{n} \mathbf{a}_k \mathbf{b}_k^T = \mathbf{a}_1 \mathbf{b}_1^T + \mathbf{a}_2 \mathbf{b}_2^T + \dots + \mathbf{a}_n \mathbf{b}_n^T$$

> What is column $i$ of A x row $j$ of B?
```math
\mathbf{a}_i 
\mathbf{b}_j^T 
= 
\begin{bmatrix} 
2 \\ 
3 \\ 
4 
\end{bmatrix} 
\begin{bmatrix} 
1 & 6 
\end{bmatrix} 
= 
\begin{bmatrix} 
2 & 12 \\ 
3 & 18 \\ 
4 & 24 
\end{bmatrix} 
```

* Columns of C are all multiple $\mathbf{a}_i$
* Rows of C are all multiple $\mathbf{b}_j^T$

### 1.5 Block
```math
\begin{bmatrix}
A_1 & A_2 \\
A_3 & A_4
\end{bmatrix}
\begin{bmatrix}
B_1 & B_2 \\
B_3 & B_4
\end{bmatrix}
=
\begin{bmatrix}
C_1 & C_2 \\
C_3 & C_4
\end{bmatrix}
```

Where the top-left block is calculated as: $C_1 = A_1 B_1 + A_2 B_3$

## 2. Inverses and Gauss-Jorden

### 2.1 Inverses (square matrices)

$$
\underbrace{A^{-1}A}_{\text{Left Inverse}} = I = \underbrace{AA^{-1}}_{\text{Right Inverse}}
$$

If $A^{-1}$ exists, the matrix $A$ is **invertible** (or **nonsingular**).

### 2.2 Singular case (no inverse)

```math
A=
\begin{bmatrix}
1 & 3 \\
2 & 6
\end{bmatrix}
```
> Why is $A$ singular?
* Determinant is 0 (not learned yet).
* Columns of $A \times ?$ are all multiples of one column of $A$, which cannot construct an identity matrix $I$.
* You can find a non-zero vector $\mathbf{x}$ with $A\mathbf{x}=\mathbf{0}$. If $A\mathbf{x}=\mathbf{0}$, $A^{-1}A\mathbf{x}=A^{-1}\mathbf{0}=\mathbf{0}$, then $\mathbf{x}$ must be zero.

### 2.3 Invertible case

```math
\underbrace{
\begin{bmatrix}
1 & 3 \\
2 & 7
\end{bmatrix}
}_{A}
\underbrace{
\begin{bmatrix}
a & c \\
b & d
\end{bmatrix}
}_{A^{-1}}
=
\underbrace{
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}
}_{I}
```
> How could you know $A$ is invertible?
* Columns of $A$ are vectors which have different directions.

> How could you understand of solving $A^{-1}$?
* $A \times columns of A^{-1} = column j of I$

