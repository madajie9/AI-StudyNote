# Lecture 1 Solving Equations and Linear Combination

1. Solving equations: n equations, n unknows

$$
\begin{cases}
\phantom{1}x + 2y + 3z = 14 \tag{1}\\
4x + 5y + 6z = 32\\
\phantom{x+1} 8y + 9z = 50
\end{cases}
$$

$$
\\[10pt]
\hspace{1em}\Downarrow\hspace{1em}
\\[10pt]
$$
 
$$
\begin{bmatrix}
 1 & 2 & 3 \\
 4 & 5 & 6 \\
 0 & 8 & 9
\end{bmatrix}
\begin{bmatrix}
 x \\
 y \\
 z
\end{bmatrix}
=
\begin{bmatrix}
 14 \\
 32 \\
 50
\end{bmatrix}
\tag{2}
$$

$$
\\[10pt]
 \hspace{1em}\Downarrow\hspace{1em}
 \\[10pt]
$$
 
$A\mathbf{x} = \mathbf{b}\tag{3}$

2. Linear combination: Another way to view the multiplication of matrices and vectors

    - $A\mathbf{x}$ : linear combination of _columns_ of  A
  $\begin{bmatrix}1 & 2 & 3 \\4 & 5 & 6 \\0 & 8 & 9\end{bmatrix}\begin{bmatrix}x\\y\\z\end{bmatrix}=x\begin{bmatrix}1\\4\\0\end{bmatrix}+y\begin{bmatrix}2\\5\\8\end{bmatrix}+z\begin{bmatrix}3\\6\\9\end{bmatrix}$
  
    - $\mathbf{x^T}A$: linear combination of _rows_ of A
  $\begin{bmatrix}x & y & z\end{bmatrix}\begin{bmatrix}1 & 2 & 3 \\4 & 5 & 6 \\0 & 8 & 9\end{bmatrix}=x\begin{bmatrix}1 & 2 & 3\end{bmatrix}+y\begin{bmatrix}4 & 5 & 6\end{bmatrix}+z\begin{bmatrix}0 & 8 & 9\end{bmatrix}$
  
3. See solving equations from the perspective of linear combination

   - Solving equations $A\mathbf{x}=\mathbf{b}$ means finding one or more linear combinations of column vectors of $A$ that is equal to $\mathbf{b}$.


# Lecture 2 Elimination and Matrices Operation
$(E_{21})A=(E_{32}E_{21})A=U$



	
	

