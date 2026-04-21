# Lecture 5 Permutation, Transpose and Vector Space

## 5.1 Permutation

### 5.1.1 $PA=LU$
Previously we got:
```math
$$
A = LU = 
\begin{pmatrix}
1      & 0      & 0      & \cdots & 0      \\
l_{21} & 1      & 0      & \cdots & 0      \\
l_{31} & l_{32} & 1      & \cdots & 0      \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
l_{n1} & l_{n2} & l_{n3} & \cdots & 1
\end{pmatrix}
\begin{pmatrix}
u_{11} & u_{12} & u_{13} & \cdots & u_{1n} \\
0      & u_{22} & u_{23} & \cdots & u_{2n} \\
0      & 0      & u_{33} & \cdots & u_{3n} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0      & 0      & 0      & \cdots & u_{nn}
\end{pmatrix}
$$
```

$P$: excute row exchanges.

Then for any invertible $A$, $A=LU$ becomes $PA=LU$.

### 5.1.2 Permutation matrix $P$

$P$ is an identity matrix $I$ with reordered rows. $n! = n(n-1) \dots (3)(2)(1)$ counts the total number of reorderings (all $n \times n$ permutation matrices).

### 5.1.3 Characteristics of $P$: $P^{-1}=P^{T}$

> $P$ is always invertible and $P^{-1}=P^{T}$, namely $P^{T}P=I$
* The effect of extrange row $i$ and row $j$ of $I$ is equal to extrange column $i$ and $j$ (switch pivot $i$ and $j$), which means that for all 2-row exchange permutation matrix $P^{T}=P$.
* The inverse of 2-row exchange permutation matrix is itself, which means that for all 2-row exchange permutation matrix $P^{-1}=P$.
* For any permutation matrix, it is the multiplication of 2-row exchange matrixs: $P=P1P2 \dots P_{n}$, in which $(P_{i})^{T}=(P_{i})^{-1}=P_{i}$
* $P^{T} = (P_{n})^{T} \dots (P_{2})^{T}(P_{1})^{T}=P_{n} \dots P_{2}P_{1} = (P_{n})^{-1} \dots (P_{2})^{-1}(P_{1})^{-1} = P^{-1} $, proved.


## 5.2 Transpose

The transpose of $A$ is defined as 
```math
A^{T}_{ij} = A_{ji}
```

Symetric matrix is defined as
```math
A_{ij}=A_{ji}
```

Symetric matrix must be square matrix, but for any matrix $R_{mxn}$, $R^{T}R$ and $RR^{T}$ are symetric because of the rule of transpose $(R^{T}R)^{T}=R^{T}R, (RR^{T})^{T}=RR^{T}$

## 5.3 Vector Space

### 5.3.1 Examples

> $R^{2}=$ all 2-dim real vectors $=$ "x-y plane"
> 
> $R^{3}=$ all 3-dim real vectors $=$ "x-y-z space"
> 
> $R^{n}=$ all columne vectors with n real components

### 5.3.2 Not a vector space

Vector space should be **closed** under multiplications and additions of vectors (linear combinations)

If we select only the first quadrant of $R^{2}$, it is not a vector space. Because vector $$\begin{bmatrix}3 \\ 2\end{bmatrix}$$ the multiplication of 

### 5.3.3 Subspace

