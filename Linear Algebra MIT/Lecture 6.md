# Lecture 6 Column Space and Null Space

# 1. Vector Space Requirement
> How to know if a space is vector space?
* If $v$ and $w$ in the space, then $v+w$ and $cv$ are in the space, which means that all combinations $cv+dw$ are in the space.

For $R^{3}$, zero vector is 
```math
\begin{bmatrix} 
0 \\ 
0 \\ 
0 
\end{bmatrix}
```

**P**lane through zero vector is a subspace of $R^{3}$

**L**ine through zero vector is a subspace of $R^{3}$

$P \cup L=$ all vectors in $P$ or $L$ or both.

$P \cap L=$ all vectors in both $P$ and $L$.

> Is $P \cup L$ a subspace?

* No. Select a vector $v$ from the line $L$ and $w$ from the plance $P$, their addition vector is absolutely not in $L$ or $P$.

> Is $P \cap L$ a subspace?

* Yes. Assume $v, w \in P$ and $v, w \in L$:
* $P$ is a vector space, so $v, w \in P \Rightarrow cv+dw \in P$.
* $L$ is a vector space, so $v, w \in L \Rightarrow cv+dw \in L$.
* Finally, we got $cv+dw \in P \cap L$.

# 2. Column Space of $A$

```math
A
=
\begin{bmatrix}
1 & 1 & 2 \\
2 & 1 & 3 \\
3 & 1 & 4 \\
4 & 1 & 5 
\end{bmatrix}
```
> What is column space of $A$, $C(A)$?
* It is a subspace of $R^{4}$ $=$ all linear combinations of columns of $A$.

```math
Ax
=
\begin{bmatrix}
1 & 1 & 2 \\
2 & 1 & 3 \\
3 & 1 & 4 \\
4 & 1 & 5 
\end{bmatrix}
\begin{bmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{bmatrix}
=
\begin{bmatrix}
b_{1} \\
b_{2} \\
b_{3} \\
b_{4}
\end{bmatrix}
=
b
```

> Does $Ax=b$ have a solution for every $b$?
* No. Because 4 equations and 3 unknowns.

> Which b's allow this sysmtem to be solved?
* Some easy think cases:
```math
b
=
\begin{bmatrix}
0 \\
0 \\
0 \\
0
\end{bmatrix}
,
b
=
\begin{bmatrix}
1 \\
2 \\
3 \\
4
\end{bmatrix}
\begin{bmatrix}
1 \\
1 \\
1 \\
1
\end{bmatrix}
\begin{bmatrix}
2 \\
3 \\
4 \\
5
\end{bmatrix}
```
> Or think of any $x$ first and do combination to get $b$
* We can solve $Ax=b$ exactly when $b$ is in $C(A)$.

# 3. Null Space of $A$

> Does each column of $A$ contribute something new? Or can I throw some columns and still keep $C(A)$?
* Yes.

> Are columns of $A$ independent?
* No. $C(A)$ is a 2-dim subspace of $R^{4}$, not 3-dim.

> What is null space of $A$, $N(A)$?
* All solutions $x$ to $Ax=0$, it is a subspace of $R^{3}$

```math
Ax
=
\begin{bmatrix}
1 & 1 & 2 \\
2 & 1 & 3 \\
3 & 1 & 4 \\
4 & 1 & 5 
\end{bmatrix}
\begin{bmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0 \\
0 \\
0
\end{bmatrix}
```

$N(A)$ contains:
```math
\begin{bmatrix}
0 \\
0 \\
0
\end{bmatrix}
\begin{bmatrix}
1 \\
1 \\
-1
\end{bmatrix}
```
, which can be concluded as:

```math
c
\begin{bmatrix}
1 \\
1 \\
-1
\end{bmatrix}
```
for any $c$.

> Why $N(A)$ is subspace?
* Check that solutions to $Ax=0$ always give a subspace.
* Assume $v,w \in N(A)$, then $Av=0, Aw=0$. $A(cv+dw)=cAv+dAw=c0+d0=0$, which means taht $cv+dw \in N(A)$.

> Do the solution of $Ax=b$ give a subspace?
* No. $b=0$ is special. $A(cv+dw)=cAv+dAw=(c+d)b\neqb$, which means that $v,w \in$ this space could not give $v,w \in$ this space.
