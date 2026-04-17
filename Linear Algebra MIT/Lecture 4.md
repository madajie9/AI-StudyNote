# Lecture 4 A=LU (no row exchanges)

> Some conclusions about inverse which will be used in this lecture
* $A$ is invertible, $B$ is invertible, then $(AB)^{-1}=B^{-1}A^{-1}$
* $A$ is invertible, then $(A^{T})^{-1}=(A^{-1})^{T}$, which comes from $AA^{-1}=I=I^{T}=(AA^{-1})^{T}=(A^{-1})^{T}A^{T} \Rightarrow (A^{-1})^{T}A^{T}=I \Rightarrow$ the inverse of $A^{T}$ is $(A^{T})^{-1}$

## 1. Gauss Elimitation -> LU Decomposition

* $L \Rightarrow$ **L**ower matrix
* $U \Rightarrow$ **U**pper matrix

### 1.1 Case 2x2
```math
\underbrace{
\begin{bmatrix}
1 & 0 \\
-4 & 1
\end{bmatrix}
}_{E_{21}}
\underbrace{
\begin{bmatrix}
2 & 1 \\
8 & 7
\end{bmatrix}
}_{A}
=
\underbrace{
\begin{bmatrix}
2 & 1 \\
0 & 3
\end{bmatrix}
}_{U}
```

```math
\underbrace{
\begin{bmatrix}
2 & 1 \\
8 & 7
\end{bmatrix}
}_{A}
=
\underbrace{
\begin{bmatrix}
1 & 0 \\
4 & 1
\end{bmatrix}
}_{L}
\underbrace{
\begin{bmatrix}
2 & 1 \\
0 & 3
\end{bmatrix}
}_{U}
```

* $E_{21}$ substracts 4xrow1 from row2 in $A$.
* $L=(E_{21})^{-1}$ adds 4xrow1 back to row2 in $U$ to recover $A$.

Another way is $A=LDU'$:
```math
\underbrace{
\begin{bmatrix}
2 & 1 \\
8 & 7
\end{bmatrix}
}_{A}
=
\underbrace{
\begin{bmatrix}
1 & 0 \\
4 & 1
\end{bmatrix}
}_{L}
\underbrace{
\begin{bmatrix}
2 & 0 \\
0 & 3
\end{bmatrix}
}_{D}
\underbrace{
\begin{bmatrix}
1 & \frac{1}{2} \\
0 & 1
\end{bmatrix}
}_{U'}
```
in which $\frac{1}{2}$ comes from:

```math
\underbrace{
\begin{bmatrix}
2 & 0 \\
0 & 3
\end{bmatrix}
}_{D}
\begin{bmatrix}
\frac{1}{2} \\
1
\end{bmatrix}
=
\frac{1}{2}
\begin{bmatrix}
2 \\
0
\end{bmatrix}
+
1
\begin{bmatrix}
0 \\
3
\end{bmatrix}
```

### 1.2 Case 3x3

$EA=E_{32}E_{31}E_{21}A=U$ (no row exchanges) $\Rightarrow$ $A=(E_{21})^{-1}(E_{31})^{-1}(E_{32})^{-1}U=LU$ 

> What does $E$ look like in case 3x3?

```math
\underbrace{
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & -5 & 1
\end{bmatrix}
}_{E_{32}}
\underbrace{
\begin{bmatrix}
1 & 0 & 0 \\
-2 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
}_{E_{21}}
=
\underbrace{
\begin{bmatrix}
1 & 0 & 0 \\
-2 & 1 & 0 \\
\color{red}{10} & -5 & 1
\end{bmatrix}
}_{E}
```

> L is the reversal operation of $E$

```math
\underbrace{
\begin{bmatrix}
1 & 0 & 0 \\
2 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
}_{(E_{21})^{-1}}
\underbrace{
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 5 & 1
\end{bmatrix}
}_{(E_{32})^{-1}}
=
\underbrace{
\begin{bmatrix}
1 & 0 & 0 \\
2 & 1 & 0 \\
\color{green}{0} & 5 & 1
\end{bmatrix}
}_{L}
```

Compared with $E$, one attractive note about $L$ is that, if no row exchanges, the minus of multipliers in each pivot position of $E$ go directly into the save position in $L$.
You don't need to calculate any entry in $L$ like $\color{red}{\text{10}}$ in $E$.

## 2. How many operations for elimination of nxn matrix $A$?

> Assume n=100

> 1 operation means 1 multiply and 1 add (entry-level)

* Count on $A$

$(n-1)n + (n-2)(n-1) + \dots + 2 \cdot 1 \approx \int_0^n x^2 dx = \frac{1}{3}n^3$

* Count on $b$

$(n-1) + (n-2) + \dots + 1 \approx \int_0^n x dx = \frac{1}{2}n^2$

## 3. Permutations (row exchanges)

For case 3x3, there is $3!=6$ Ps

* Identity
```math
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
```
* Transpose is themselves, and inverse is also themselves (exchange 2 rows, the inverse is to exchange them back)
```math
\begin{bmatrix}
0 & 1 & 0 \\
1 & 0 & 0 \\
0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
0 & 0 & 1 \\
0 & 1 & 0 \\
1 & 0 & 0
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 \\
0 & 0 & 1 \\
0 & 1 & 0
\end{bmatrix}
```
* Inverses are Transposes
```math
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
1 & 0 & 0
\end{bmatrix}
\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0
\end{bmatrix}
```

> Why inverses are transposes?

* Because these matrixs are the multiplication of two 2rows-exchange permutation matrixs, assuming $P_{3}=P_{1}P_{2}$
* in which $P_{1}$ and $P_{2}$ satisfy "transpose is themselves, and inverse is also themselves".
* That way, we have $(P_{3})^{-1}=(P_{2})^{-1}(P_{1})^{-1}=P_{2}P_{1}$ as well as $(P_{3})^{T}=(P_{2})^{T}(P_{1})^{T}=P_{2}P_{1}$
* Then we got $(P_{3})^{-1}=P_{2}P_{1}=(P_{3})^{T}$.

