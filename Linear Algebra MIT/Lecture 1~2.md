# Lecture 1 Solving Equations and Linear Combination

1. Solving equations: n equations, n unknowns

$$
\begin{cases}
 \mkern 8mu x + 2y + z &= 2 \\
 3x + 8y + z &= 12\\
 \mkern 42mu 4y + z &= 2
\end{cases} \quad(1)
$$

$$
\hspace{1em}\Downarrow\hspace{1em}
$$

$$
\begin{bmatrix}
 1 & 2 & 1 \\
 3 & 8 & 1 \\
 0 & 4 & 1
\end{bmatrix}
\begin{bmatrix}
 x \\
 y \\
 z
\end{bmatrix}
\=
\begin{bmatrix}
 2 \\
 12 \\
 2
\end{bmatrix}
$$

$$
\hspace{1em}\Downarrow\hspace{1em}
$$
 
$$
A\mathbf{x} = \mathbf{b}
$$

2. Linear combination: another way to view the multiplication of matrices and vectors
   - $A\mathbf{x}$: linear combination of _columns_ of A
     ```
     [ 1  2  1 ] [x]     [1]     [2]     [1]
	 [ 3  8  1 ] [y] = x [3] + y [8] + z [1]
	 [ 0  4  1 ] [z]     [0]     [4]     [1]
    - $\mathbf{x^T}A$: linear combination of _rows_ of A
	  ```
             [ 1  2  1 ]
	  [x y z][ 3  8  1 ] = x [1 2 1] + y [3 8 1] + z [0 4 1]
	         [ 0  4  1 ]
3. See solving equations from the perspective of linear combination
   - Solving equations $A\mathbf{x}=\mathbf{b}$ means finding one or more linear combinations of column of $A$ that is equal to $\mathbf{b}$.
   - Can I solve $A\mathbf{x}=\mathbf{b}$ for every $\mathbf{b}$? $\Rightarrow$ Do the linear combinations of the columns of $A$ fill 3-D space? $\Rightarrow$ Singular? Invertible?


# Lecture 2 Elimination and Matrices Operation
1. Elimination: privot (2,1), (3,2)
   
$$
\begin{bmatrix}
 1 & 2 & 1 & 2 \\
 3 & 8 & 1 & 12 \\
 0 & 4 & 1 & 2
\end{bmatrix}
\hspace{1em}\overset{\text{(2,1)}}{\Rightarrow}\hspace{1em}
\begin{bmatrix}
 1 & 2 & 1 & 2 \\
 0 & 2 & -2 & 6 \\
 0 & 4 & 1 & 2
\end{bmatrix}
\hspace{1em}\overset{\text{(3,2)}}{\Rightarrow}\hspace{1em}
\begin{bmatrix}
 1 & 2 & 1 & 2 \\
 0 & 2 & -2 & 6 \\
 0 & 0 & 5 & -10
\end{bmatrix}
$$

2. Substitution: equations (1) becomes (2), solve in order $z=-2$, $y=1$ and $x=2$

$$
\begin{cases}
 \mkern 8mu x + 2y + \mkern 8mu z &= 2 \\
 \mkern 40mu 2y - 2z &= 6\\
 \mkern 82mu 5z &= -10
\end{cases} \quad(2)
$$

3. Elementary matrices: elimination, permutation
   - $E_{21}$: subsract 3xrow1 from row2 of $A$ by $E_{21}A$
     ```
     [  1  0  0 ]
     [ -3  1  0 ]
     [  0  0  1 ]
   - $E_{32}$: subsract 2xrow2 from row3 of $A$ by $E_{32}A$
     ```
     [ 1   0  0 ]
     [ 0   1  0 ]
     [ 0  -2  1 ]
4. Matrix multiplication and associative laws
   - $E_{32}(E_{21}A)=(E_{32}E_{21})A=U$





	
	

