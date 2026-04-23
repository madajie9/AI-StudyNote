# Lecture 7 Computing the Nullspace

Solving $Ax=0$

Pivot variables - free variables

Special solutions - $rref(A)=R$

```math
A=
\begin{bmatrix}
1 & 2 & 2 & 2 \\
2 & 4 & 6 & 8 \\
3 & 6 & 8 & 10
\end{bmatrix}
```

## 1. Elimination Does Not Change Nullspace

Elimination of A is achieved by row operations, which will change the columns space of $A$, but not change the nullspace of $A$ (the solution of $Ax=0$ will not change).

> Why change column space?

* Take an example. The column spaces of $A$ could be constructed by linear combinations of:
```math
c
\begin{bmatrix}
1 \\
2 \\
3
\end{bmatrix}
+
d
\begin{bmatrix}
2 \\
6 \\
8
\end{bmatrix}
```

,***which is a plane in $R^3$***.

When apply operation of rows like $E =$ "substract row1 and row2 from row3", row3 becomes all zeros, 

```math
EA=
\begin{bmatrix}
1 & 2 & 2 & 2 \\
2 & 4 & 6 & 8 \\
0 & 0 & 0 & 0
\end{bmatrix}
```

which means that the vector in this column space $C(EA)$ will always get zero on the third component. It is constructed by linear combinations of:
```math
c
\begin{bmatrix}
1 \\
2 \\
0
\end{bmatrix}
+
d
\begin{bmatrix}
2 \\
6 \\
0
\end{bmatrix}
```
,***which is a plane in $R^3$ totally different from the previous one. It is special for orthognal to z-axis***.

> Why not change nullspace?

* $Ax=0 \Rightarrow (EA)x=E(Ax)=0 \Rightarrow x \in N(EA)$
* $E$ is invertible, $(EA)x=0 \Rightarrow E(Ax)=(EA)x=0 \Rightarrow Ax=E^{-1}0=0 \Rightarrow x \in N(A)$ 

## 2. Solving $Ax=0$ by Elimination

```math
A=
\begin{bmatrix}
\color{red}{1} & 2 & 2 & 2 \\
2 & 4 & 6 & 8 \\
3 & 6 & 8 & 10
\end{bmatrix}

\Rightarrow

\begin{bmatrix}
\color{red}{1} & 2 & 2 & 2 \\
0 & 0 & \color{red}{2} & 4 \\
0 & 0 & 2 & 4
\end{bmatrix}

\Rightarrow

\begin{bmatrix}
\color{red}{1} & 2 & \color{red}{2} & 2 \\
\color{red}{0} & 0 & \color{red}{2} & 4 \\
\color{red}{0} & 0 & \color{red}{0} & 0
\end{bmatrix}

=U

```

The shape of matrix $A$ is $mxn$, $m$ rows $n$ columns.

The number of pivots are 2 $\Rightarrow$ the rank of $A$, $r = 2$ $\Rightarrow$ the number of pivot columns are 2.

The number of free columns is the number column number minus the pivot columns number $=n-r=4-2=2$. 

Free columns 2 and 4 means $x_2, x_4$ could be any values; Once you choose the values of free $x_2, x_4$, the pivot $x_1, x_3$ should be fixed to solve $Ux=0$ as well as $Ax=0$.

## 3. Special Solutions




## 4. Reduced Row Echelon Form $R$ and Nullspace Matrix $N$


