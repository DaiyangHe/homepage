**Author**: Dylan He
# Geometric explaination of equations system
## Vectors and Linear Combination
The equations system can be written as the linear combination of two vectors, which can be expressed in the means of the matrix. For example,
$$
\begin{equation}
    \begin{cases}
        2x-y=0\\
        -x+2y=0
    \end{cases}
\end{equation}
$$
can be also written as:
$$
\begin{equation}
    \begin{bmatrix}
        2 & -1\\
        -1 & 2 
    \end{bmatrix}
    \begin{bmatrix}
        x\\
        y
    \end{bmatrix}
    =
    \begin{bmatrix}
        0\\
        3
    \end{bmatrix}
\end{equation}
$$
We can view this equation system in two pictures. For the **Row Picture**, $x$ and $y$ are the locations of the point that is passed through by two straight lines $2x-y=0$ and $-x+2y=0$. However, with the **column picture**, finding $x$ and $y$ is to find a linear combination of two vectors to make it equals to another vector. That is:
$$
\begin{equation}
    x
    \begin{bmatrix}
        2\\
        -1
    \end{bmatrix}
    +y
    \begin{bmatrix}
        -1\\
        2
    \end{bmatrix}
    =\begin{bmatrix}
        0\\
        3
    \end{bmatrix}
\end{equation}
$$
So solving an equation system is the problem that finding a proper linear combination of two given vectors to produce a new given vector. Now there is a new question: Can we solve all **$Ax=b$** for every $b$? In other words, **Do the linear combinations of the column fill the whole 3-dimensional space?** The answer depends on different $A$. For this special matrix (both non-singular and invertible), the answer is yes. Otherwise, the linear combination cannot fill the whole space, no matter whether it's 3-dimensional or not.
## the matrix representation of equation systems
The equation systems can be considered as the linear combination of the columns of a matrix $A$. That is:
$$
\begin{equation}
    \textbf{Ax=b}
\end{equation}
$$
# Elimination
## Gaussian Elimination
The process of elimination is to transfer the original matrix **A** into an up-triangle matrix **U** according to three pivots. In the meantime, add **b** into the original matrix, we can get the **Augmented Matrix**.
$$
\begin{equation}
    \begin{bmatrix}
    2 & -1 & 0\\
    -1 & 2 & 3
    \end{bmatrix}
\end{equation}
$$

Applying Gaussian Elimination to the augmented matrix we can get a new equation: **Ux=C**, which is easy to solve by back-substitution.
## Operation in Matrix Form
Considering the example:
$$
\begin{equation}
    \begin{cases}
        x+2y+z=2\\
        3x+8y+z=12\\
        4y+z=2
    \end{cases}
\end{equation}
$$
we can write the matrix:
$$
\begin{equation}
    \mathbf{A}=
    \begin{bmatrix}
        1 & 2 & 1\\
        3 & 8 & 1\\
        0 & 4 & 1
    \end{bmatrix}
\end{equation}
$$
In order to transfer it to:
$$
\begin{equation}
    \mathbf{C}=
    \begin{bmatrix}
        1 & 2 & 1\\
        0 & 2 & -2\\
        0 & 0 & 5
    \end{bmatrix}
\end{equation}
$$
we can consider using some matrix to multiply it. To eliminate the element (2, 1), we name the matrix $E_{21}$.
$$
\begin{equation}
    \mathbf{E_{21}A}=
    \begin{bmatrix}
        1 & 2 & 1\\
        0 & 2 & -2\\
        0 & 4 & 1
    \end{bmatrix}
\end{equation}
$$
Then, we use $E_{32}$ to eliminate the element (3, 2).
$$
\begin{equation}
    \mathbf{E_{32}(E_{21}A)=(E_{32}E_{21})A}=
    \begin{bmatrix}
        1 & 2 & 1\\
        0 & 2 & -2\\
        0 & 0 & 5
    \end{bmatrix}
\end{equation}
$$
Where 
$$
\begin{equation}
    \mathbf{E_{21}}=
    \begin{bmatrix}
        1 & 0 & 0\\
        3 & 1 & 0\\
        0 & 0 & 1
    \end{bmatrix}
    ,\quad \mathbf{E_{32}}=
    \begin{bmatrix}
        1 & 0 & 0\\
        0 & 1 & 0\\
        0 & -2 & 1
    \end{bmatrix}
\end{equation}
$$
A permutation matrix can exchange the rows or columns of a matrix. Take a $2\times 2$ matrix as an example.
$$
\begin{equation}
    \mathbf{P} = \begin{bmatrix}
        0 & 1\\
        1 & 0
    \end{bmatrix}
    \mathbf{A} = \begin{bmatrix}
        a & b\\
        c & d
    \end{bmatrix}
\end{equation}
$$
We can see that the rows of A will be exchanged if $\mathbf{P}$ multiplies on the left, and the columns operation will be done if $\mathbf{P}$ multiplies on the right.
# Matrix Multiplication and Inverses
## Matrix Multiplication
Considering the matrix $\mathbf{AB=C}$, each element in the result **C** is given by:
$$
    C_{ij}=\sum_{k=1}^{n}A_{ik}B_{kj}
$$
Therefore, multiplication is feasible only for a pair of matrices like $m\times n$ and $n\times p$ shape.
Also, we can consider each element of **C** as a result of dot production between two vectors stored in **A** and **B**. Rows of **C** are the linear combination of columns of **B**. In the meantime, the columns of **C** are the linear combination of rows of **A**.
Additionally, the matrix can be divided into blocks, and each block can be considered as an element and then conduct multiplication.
## Inverses
$\mathbf{A^{-1}}$ is the inverse matrix of **A**, which satisfies:
$$

    \mathbf{A^{-1}A=I}
$$

Where **I** is the identity matrix. Specially, for square matrix,
$$

    \mathbf{A^{-1}A=AA^{-1}=I}
$$
A singular matrix is not invertible. Take a $2\times 2$ matrix as an example:
$$
\begin{equation}
    A = 
    \begin{bmatrix}
        1 & 3\\
        2 & 6
    \end{bmatrix}
\end{equation}
$$
Its determinant equals to 0. Besides, we can say that the singular matrix for which a non-zero vector **X** such that $\mathbf{AX=0}$ can be found cannot be invertible. For **A**, we can find:
$$
\begin{equation}
    \mathbf{AX}=
    \begin{bmatrix}
        1 & 3\\
        2 & 6
    \end{bmatrix}
    \begin{bmatrix}
        3\\
        -1
    \end{bmatrix}
    =\begin{bmatrix}
        0\\
        0
    \end{bmatrix}
\end{equation}
$$
Now, we assume A has an inverse. Then we multiply it on both sides of the equation. 
$$
\begin{equation}
    \mathbf{A^{-1}(AX)=(A^{-1}A)X=X=A^{-1}0=0}
\end{equation}
$$
So $\mathbf{X=0}$. However, as we mentioned before, $\mathbf{X\neq0}$. So the original assumption is wrong, the singular matrix is not invertible.

Let we define the determinant of a matrix:
$$
\mathbf{A}=\begin{bmatrix}
a&b\\
c&d
\end{bmatrix}
$$
Its determinant is defined as:
$$
\mathrm{det}(\mathbf{A})=ad-bc
$$
While the inverse of matrix $\mathbf{A}$ can be calculated by:
$$
A^{-1}=\frac{1}{\text{det}(A)} \begin{bmatrix}
d&-b\\
-c&a
\end{bmatrix}
$$
Overall, following statements are equivalent:
* A is invertible
* Ax=b has a unique solution for every b in $R^n$
* Ax=0 has only a trivial solution
* The reduced raw echelon is $I_n$
* A is a product of elementary matrix
* $\det A\neq 0$, and all eigenvalues are nonzero
## Gauss-Jordan Elimination
The Gauss-Jordan idea suggests that we operate elimination on the augmented matrix to gain an identity matrix in the place of the coefficient matrix, and then we will get the inverse of **A** in the place of the identity matrix.

Let's consider the elimination process as a multiplication that **E** times
augmented matrix.
$$
\begin{equation}
    \mathbf{E}\begin{bmatrix}
        A&I
    \end{bmatrix}
    =\begin{bmatrix}
        I&EI
    \end{bmatrix}
\end{equation}
$$
We know that $\mathbf{EA=I}$, so $\mathbf{E=A^{-1}}$ and $\mathbf{EI=A^{-1}}$.
# LU Factorization
## Transpose and Inverses
The inverse of A transpose equals the transpose of A inverse.
$$
    (\mathbf{A^{-1}})^T=(\mathbf{A^T})^{-1}
$$
The inverse of the multiplication of matrices **AB** is the inverses of them in reverse order.
$$
    \mathbf{ABB^{-1}A^{-1}=I}
$$
## LU Factorization
Let the matrix U be the result of the process of the Gaussian elimination of the matrix A.
$$
    \mathbf{EA=U}
$$
where A is an upper-triangle matrix. Then the process can be also written as:
$$
    \mathbf{A=E^{-1}U}
$$
Let $\mathbf{L}=E^{-1}$. Where L is a lower-triangle matrix. Thus any matrix can be factorized into a product of a lower-triangle matrix and an upper-triangle matrix.
$$
    \mathbf{A=LU}
$$
To find matrix $\mathbf{L}$, there is no problem to apply Gauss-Jordan Elimination. However, there are several easy ways. Considering the example $$A=\begin{bmatrix}
2&-1&3 \\
4&-1&3 \\
-2&5&5 \\
\end{bmatrix}$$
to find its LU factorization, we perform following row operations sequentially.
- $R_{2}-2R_{1}$
- $R_3-(-1)R_1$
- $R_3-(-2)R_2$
The multipliers are precisely the entries of $\mathbf{L}$ that are below its diagonal.
$$
L=\begin{bmatrix} 
1&0&0 \\
2&1&0 \\
-1&-2&1
\end{bmatrix}
$$
In applying this method, it is important to note that the elementary row operations $R_i-kR_j$ must be performed from top to bottom within each column (using the diagonal entry as the pivot), and column by column from left to right. Otherwise the wrong result will be got.
Assume  $Ux=y$, the original linear system can be written as $$L(Ux)=Ly=b$$Thus solving the original linear system can be completed by solving two equations $Ly=b,\ Ux=y$.
### $P^T$ $LU$ Factorization
For a matrix that row interchanges are necessary to perform $LU$ factorization, we can simply multiply a permutation matrix like:
$$
P=
\begin{bmatrix}
1&0&0 \\
0&0&1 \\
0&1&0
\end{bmatrix}
$$
which means exchange row 2 and row 3. It's easy to prove $P^T=P^{-1}$. Therefore, for such matrix, the LU factorization can be performed as:
$$
A=P^{T}LU
$$
Every square matrix has a $P^TLU$ factorization.
# Permutation, Transposition, and Vector Space
## Permutation
A permutation matrix is an identity matrix with reordered rows. For any invertible matrix, we have the normal forms of LU factorization.
$$
    \mathbf{PA=LU}
$$
All permutation matrices are invertible, the inverses of permutation matrices are equal to their transposition.
$$
    \mathbf{P^T P=I}
$$
## Transposition
The definition of transposition is:
$$
    \mathbf{A}^{T}_{ij}=\mathbf{A}_{ji}
$$
The symmetric matrix is a special matrix such that transposition doesn't change anything to them.
$$
    \mathbf{R^T=R}
$$
For any matrix A, $\mathbf{R=A^T A}$ is symmetric. Just like the inverse, transposition owns a property:
$$
    \mathbf{(AB)^T=B^T A^T}
$$
## Vector Space
A vector space is a set of vectors that satisfy some properties. In detail, a vector space is closed to addition and scalar multiplication, which means the results of operations like addition or scalar multiplication on any vector in the space are still in this space. For example, $\mathbf{R^3}$ is a vector space.

A subspace is also a vector space included by a larger vector space. For instance, any straight line passing through the origin is a subspace of $\mathbf{R^N}$ for $n\leq 2$. It's also clear that the origin must be included in any vector space. In fact, the origin point itself is a vector space.

A $n-1\times n$ matrix containing column vectors represents a plane passing through the origin. All the linear combinations of those vectors form a subspace in $\mathbf{R^n}$.
# Column Space and Null Space
## Properties of Subspace
We can see that for subspaces **P** and **L**, $\mathbf{P\cup L}$ is not necessarily to be a vector space, but $\mathbf{P\cap L}$ must be a smaller subspace.
## Column Space
The column space provides us with a new way to view the linear equations **Ax=b**. Considering an example:
$$
\mathbf{A}=
    \begin{bmatrix}
        1 & 1 & 2\\
        2 & 1 & 3\\
        3 & 1 & 4\\
        4 & 1 & 5
    \end{bmatrix}
$$
We can see that the linear equations:
$$
  \begin{bmatrix}
        1 & 1 & 2\\
        2 & 1 & 3\\
        3 & 1 & 4\\
        4 & 1 & 5
    \end{bmatrix}
    \begin{bmatrix}
        x_1\\
        x_2\\
        x_3
    \end{bmatrix}
    =\begin{bmatrix}
        b_1\\
        b_2\\
        b_3 \\
        b_{4}
    \end{bmatrix}
$$
contains 4 equations but only 3 unknowns. So the solution does not always exist for any **b**.

In order to indicate what **b** is proper to make the solution exist, we need to consider the geometric explanation of **Ax=b**. only when the vector **b** is a linear combination of column vectors, which means **b** is inside of column space, the only **x** can be found. For this example, the column space is a 2-D plane in $R^4$.
## Null Space
Null space of **A** is all solution **x** such that **Ax=0**. For the previous example, the null space of **A** is the solution to:
$$
\begin{bmatrix}
        1 & 1 & 2\\
        2 & 1 & 3\\
        3 & 1 & 4\\
        4 & 1 & 5
    \end{bmatrix}
    \begin{bmatrix}
        x_1\\
        x_2\\
        x_3
    \end{bmatrix}
    =\begin{bmatrix}
        0\\
        0\\
        0
    \end{bmatrix}
$$
We can solve the equation easily.
$$
    \mathbf{x}=c
    \begin{bmatrix}
        1\\
        1\\
        -1
    \end{bmatrix}
    , \quad c\in \mathbb{Z}
$$
We can see that all **x** give a subspace (a straight line). It's also easy to check that all solutions to linear equations like **AX=0** must give a subspace.

The column space and the null space are both important ways to build a subspace.
# Solving linear equations
## Solving $Ax=0$: Pivot Variables and Special Solution
Let's begin with an example:
$$
   \mathbf{A}=
    \begin{bmatrix}
        1 & 2 & 2 & 2\\
        2 & 4 & 6 & 8\\
        3 & 6 & 8 & 10
    \end{bmatrix}
    
$$
By conducting elimination, we can have an echelon matrix:
$$
\mathbf{U}=
    \begin{bmatrix}
        1 & 2 & 2 & 2\\
        0 & 0 & 2 & 4\\
        0 & 0 & 0 & 0
    \end{bmatrix}
$$
We can see that it contains only 2 pivots in the locations of (1, 1) and (3, 2). We call the number of pivots of a matrix as rank. For **U**, its rank equals to 2. The column with a pivot is the pivot column, others are free columns. Additionally, the ranks of matrices **A** and $\mathbf{A^T}$ are the same.

Before moving on, we can work harder on **U** to get a cleaner form: Reduced Row Echelon Form. Continue to eliminate upward to make sure elements above pivots are also zero, then conduct scalar multiplication on rows to reduce pivots to 1. After that, we have rref of A:
$$
\mathbf{R}=\begin{bmatrix}
        1 & 2 & 0 & -2\\
        0 & 0 & 1 & 2\\
        0 & 0 & 0 & 0
    \end{bmatrix}
$$
A rref has zeros above and below all pivots equal to 1. Then, we continue to solve **Rx=0**.
We know that each component of the solution **x** is associated with a column. Those components corresponding to pivot columns are pivot variables, and others are free variables. For this example, $x_2$ and $x_4$ are free variables. When we conduct back substitution, any number can be assigned to free variables. For example, we assign that $x_2=1, x_4=0$ and $x_2=0, x_4=1$. We can get the pivot variables and a solution vector, which is called a special solution, separately. Then the null space of A, or solutions to **Ax=0**, are the linear combinations of special solutions.
$$
    \mathbf{x}=c
    \begin{bmatrix}
        -2\\
        1\\
        0\\
        0
    \end{bmatrix}
    +d\begin{bmatrix}
        2\\
        0\\
        -2\\
        1
    \end{bmatrix}
    
$$
The number of special solutions needed equals the number of free variables.

In fact, the previous steps are well-designed. Let's consider the general form of this question. A typical rref can be written as:
$$
\begin{bmatrix}
        I & F\\
        0 & 0\\
    \end{bmatrix}
    
$$
Then we let **N** to be the null space matrix. All linear combinations of its columns form the null space. According to back substitution, we have:
$$
\mathbf{N}=
    \begin{bmatrix}
        -F\\
        I'
    \end{bmatrix}
    
$$
Each column of **N** is a special solution. For the previous example, we can temporarily exchange columns to get a typical form, as long as we remember to exchange them back.
## Solving $Ax=b$: Solvability and Solution Set
As we mentioned before, $\mathbf{Ax=b}$ is solvable only when vector **b** is inside of the column space of **A**. In other words, if a combination of rows gives a zero row, the same combination of **b** must be 0. Consider the example before. The augmented matrix is:
$$
\mathbf{A}=
    \begin{bmatrix}
        1 & 2 & 2 & 2 & b_1\\
        2 & 4 & 6 & 8 & b_2\\
        3 & 6 & 8 & 10 & b_3
    \end{bmatrix}
    
$$
By elimination, we have:
$$
  \begin{bmatrix}
        1 & 2 & 2 & 2 & b_1\\
        0 & 0 & 2 & 4 & b_2-2b_1\\
        0 & 0 & 0 & 0 & b_3-b_2-b_1
    \end{bmatrix}
    
$$
It requires $b_3-b_2-b_1=0$. Let's say $b_1=1,b_2=5,b_3=6$. Here are the steps to find complete solutions to **Ax=b**.
* Set all free variables to 0 to find a particular solution $\mathbf{x_p}$.
* Find the null space $\{\mathbf{x_n}\}$
* The complete solution $\mathbf{x=x_p+x_n}$

For the previous example:
$$
    \mathbf{x}=\begin{bmatrix}
        -2\\
        0\\
        1.5\\
        0
    \end{bmatrix}
    +c\begin{bmatrix}
        -2\\
        1\\
        0\\
        0
    \end{bmatrix}
    +d\begin{bmatrix}
        2\\
        0\\
        -1\\
        1
    \end{bmatrix}
    
$$
The basis vectors inside the null space are also called the "Fundamental system of solutions".

For a $m\times n$ matrix, its rank $r\leq \mathrm{min}\{m,\ n\}$. The solvability depends on the rank of the matrix.

* Full rank square matrix ($r=m=n$)
  In that case, the rref is an identity matrix, it has a unique solution for any **b**.
* Full column rank ($r=n<m$)
  $$
    \mathrm{rref}=\begin{bmatrix}
            I\\
            0
        \end{bmatrix}
   $$
    
  It has 0 or 1 solution.
* Full row rank ($r=m<n$, or $r<\mathrm{min}\{m,\quad n\}$)

    $$
       \mathrm{rref}=\begin{bmatrix}
            I & F\\
            0 & 0
        \end{bmatrix}
        \qquad \text{(typical form)}
    $$
    0 or infinitely many solutions.

# Linear Independence, Basis, and Dimension
## Linear Independence
A bunch of vectors $\mathbf{x_1, x_2, \ldots, x_n}$ are independent if no combination of them gives a zero vector, except all coefficients are zero. When m-D vectors $\mathbf{v_1, v_2,\ldots,v_n}$ are column vectors in matrix **A**, they are independent if the null space of **A** contains only zero vector, which means no nonzero vector **c** such that **Ac=0**.

It can also judged by rank. If rank $=n$, it has no free variables, then they are independent. If rank $<n$, it has free variables and they are dependent.
## Basis and Dimension
When we say a bunch of vectors span a space, it means that the space contains all linear combinations of those vectors. The basis of a space is a sequence of vectors $v_1,v_2,\ldots,v_l$ with two properties:

* They are independent.
* item They span the space.

$\mathbf{R}^n$ is a vector space that n vectors that give a basis if the $n\times n$ matrix with those columns is invertible. Given a space, all bases for this space have the same number of vectors. The number of basis vectors required to span the space is the dimension of the space. \vspace{1ex}

The dimension of the column space equals the rank of the matrix.
$$
    \text{dim}\ C(\mathbf{A})=\text{rank}
$$
The dimension of null space is the number of free variables.
$$
    \text{dim}\ N(\mathbf{A})=n-\text{rank}
$$
# Four Basic subspace
For a $m\times n$ matrix, four subspaces exist.

* Column Space: All combinations of column vectors in **A**. $C(\mathbf{A})$ in $\mathbf{R}^m$
* Null Space: Solutions of **Ax=0**. $N(A)$ in $\mathbf{R}^n$
* Row Space: All combinations of row vectors in **A**, or column vectors in $\mathbf{A^T}$. $C(\mathbf{A}^T)$ in $\mathbf{R}^n$
*  Left Null Space: Null space of **A** transpose. $N(\mathbf{A}^T)$ in $\mathbf{R}^m$

Obviously, the dimension of row space is also the rank. That's because the rank of **A** and $\mathbf{A^T}$ is the same. The dimension of the left null space is also the number of free variables of $\mathbf{A^T}$.
$$
    \text{dim}\ C(\mathbf{A^T})=\text{rank}
$$
$$
    \text{dim}\ N(\mathbf{A^T})=m-\text{rank}
$$
The natural basis of $C(\mathbf{A^T})$ is the first rank row in rref, which means row spaces of **A** and its rref are the same, $C(\mathbf{A^T})=C(\mathbf{R^T})$, while $C(\mathbf{A})\neq C(\mathbf{R})$. That's because row vectors after elementary operations on rows are the combinations of previous row vectors. So they stay in the row space.

$N(\mathbf{A^T})$ is called left null space because vectors in it, let's say **y**, satisfy $\mathbf{A^T y=0}$, which can be written as $\mathbf{y^T A=0}$:
$$
    [\ y^T\ ]\mathbf{A}=0
$$
The basis of left null space can be found by Gauss-Jordan elimination.
$$
\begin{bmatrix}
        A & I
    \end{bmatrix}
    =\begin{bmatrix}
        R & E
    \end{bmatrix}
$$
We know that **EA=R** and free rows in rref is 0. The row vectors in **E** correspond to zero row vectors in rref are the basis.
# Introduction to Linear Transformations
A $m\times n$ matrix can be seen as a linear transformation that transforms a n-d vector space to a maximum $\text{min}\{m,n\}$ dimension subspace in m-dimension space. A linear transformation $T$ can be denoted as
$$
T(x)=Ax
$$
To verify a transformation $T$ is a linear transformation, we need to prove that
 $$T(c_{1}u+c_{2}v)=c_{1}T(u)+c_{2}T(v)$$
 It's obvious that linear a transformation is just perfectly equivalent to a matrix in some sense.
# Orthogonality
## Orthogonality of Vectors and Subspaces
 A couple of orthogonal vectors is vectors such that the angle between them is a right angle. For orthogonal vectors **x** and **y**:
 $$
     x^T\cdot y=0\quad \text{and} \quad ||x||^2+||y||^2=||x+y||^2
 $$
 A subspace **S** is orthogonal to another subspace **T** means that every vector in **S** is orthogonal to every vector in **T**. This requires two orthogonal subspace must have no intersection excepting the zero point. The orthogonal complement means a subspace contains all orthogonal vectors of another subspace.
Recalling the equation: $\mathbf{Ax=0}$, we can see that:

* Row space $C(A^T)$ is orthogonal complements to the null space $N(A)$
* Column space $C(A)$ is orthogonal complements to the left null space $N(A^T)$

## Projection
For vectors **u** and **v**, the projection of **v** onto **u** is given by:
$$
    proj_u(v)=\frac{u^Tv}{u^Tu}\mathbf{u}
$$


# Midterm Tutorial
### Problem 6
$$A=\begin{bmatrix}
2&1&0 \\
1&0&-1 \\
0&2&1 \\
\end{bmatrix}$$
(a) express the column space of A
$$
\text{col}(A)=\text{span}\left\{\begin{bmatrix}
2 \\1 \\0
\end{bmatrix}\begin{bmatrix}
1 \\0 \\2
\end{bmatrix}\begin{bmatrix}
0 \\-1 \\1
\end{bmatrix}\right\}=\mathbb{R}^{3}
$$
(b) find a basis of it

(c) determine if $\begin{bmatrix}2\\3\\1\end{bmatrix}$ is in the column space
because $<2,3,1> \in\mathbb{R}^3$, it's in the column space
(d) find the null space of it
Only point $(0,0,0)$ is the null space.
### Problem 8
Find the standard matrix of the following transformation $\mathbb{R}^2 \Rightarrow \mathbb{R}^2$ clockwise rotation $90\degree$ 
# Determinate a Eigenvalue
## Determinate
### Definition
The determinant is a scalar value that is computed from a square matrix. It is a key concept in linear algebra used to solve systems of linear equations, find eigenvalues, and understand matrix properties. For a square matrix $A$, the determinant is denoted as $\text{det} A$.
### Basic Properties of Determinants
1. If $A$ has a zero column (row) or has two identical rows or columns, $\det A=0$
2. If $A$ is a triangular matrix (upper or lower triangular), then:$$\det A=\prod_{i=1}^na_{ii}$$
3. Interchanging to column (row) can change the sign of $\det A$
4. If $B$ is obtained by multiply a column (row) by $k$, $\det B=k\det A$
5. Elementary Row Operation does not change determinate.
6. For square matrices $A,\ B$: $\det (AB)=(\det A)(\det B)$
7. For invertible matrix $A$: $\det(A^{-1})=\frac{1}{\det(A)}$
8. The determinant is equal to the sum of the products of the elements of any row (column) of it and its corresponding algebraic remainder.
### Recursive Calculation
For a $2\times2$ matrix: $$A=\begin{bmatrix}a&b\\c&d\end{bmatrix},\quad\det(A)=ad-bc$$
For a $n\times n$ matrix, the n-1 order determinant formed by canceling out the elements in row $i$ and column $j$ where the element $a_{ij}$ is located, and the remaining element does not change the original order is called the cofactor $M_{ij}$ of element $a_{ij}$.
Using Laplace Expansion of $A$ by the $i$th row, we have:
$$\det(A)=\sum^n_{j=1}(-1)^{i+j}a_{ij}\cdot\det(M_{ij})$$

1. **Row Reduction**:
    - Use elementary row operations to simplify AAA to triangular form and then compute the determinant as the product of diagonal entries.
    - Keep track of row swaps (change the sign).
2. **Expansion by Minors**:
    - Select a row or column with the most zeros to minimize computation.
3. **Using Properties**:
    - Factor matrices, block diagonal matrices, etc., reduce the computation.
## Eigenvalues and Eigenvectors

### Definition

Given a square matrix $A$, an **eigenvalue** $\lambda$ and a corresponding **eigenvector** $\mathbf{v} \neq \mathbf{0}$ satisfy:$$A\mathbf{v}=\lambda \mathbf{v}$$
### Characteristic Equation
To find eigenvalues, solve:
$$\det(A-\lambda I)=0$$
When eigenvalues are obtained, we can solve the linear system as follows for each $\lambda$ to get corresponding eigenvectors.
$$(A-\lambda I)\mathbf{v}=0$$Solution space, or the null space of $A-\lambda I$ is the eigenspace of $\lambda$, denoted by $E_{\lambda}$.
### Properties of Eigenvalues
1. The sum of the eigenvalues equals the trace of $A$: $\sum \lambda_i = \text{tr}(A)$
2. The product of the eigenvalues equals the determinant of $A$: $\prod \lambda_i = \text{det}(A)$.
3. If $A$ is triangular, its eigenvalues are the diagonal entries.
4. Eigenvalues of $A^T$ are the same as those of $A$
### Lemma 1: Determinant of Transpose
$$\det(A^T)=\det(A)$$
### Lemma 2: Determinant and Inverses

If $A$ is invertible:$$\det(A^{-1})=\frac1{\det(A)}$$
### Lemma 3: Determinant and Cofactors
$$\det(A)=\sum_{i=1}^na_{ij}C_{ij}\quad\text{(Cofactor expansion along column }j\text{ or row }i)$$
### Cramer's Rule
For linear system $Ax=b$, replace the $i$th column of $A$ to obtain new matrix $B_{i}$.$$A\begin{bmatrix}
x_{1}&0&0 \\
x_{2}&1&0 \\
x_{3}&0&1
\end{bmatrix}=\begin{bmatrix}
b&a_{2}&a_{3}
\end{bmatrix}=B_{1}$$the $i$th component of $x$ can be find by$$x_{i}=\frac{\det B_{i}}{\det A}$$
Absolute value of $\det A$, where $A$ is a $3\times 3$ matrix, is the volume of box composed by column vectors of $A$.
### Positive Definite Matrix
#### Definition
A **real symmetric matrix** $A$ of size $n\times n$ is said to be positive definite if, for all non-zero
vectors $\mathbf{x}\in\mathbb{R}^n$, the following condition holds:$$\mathbf{x}^TA\mathbf{x}>0$$That is, for any non-zero vector x, the quadratic form $\mathbf{x}^TA\mathbf{x}$ is always positive. This condition ensures that the matrix $A$ "stretches" vectors in a way that produces a strictly positive result when squared.
#### Properties

-  **Symmetry**: A positive definite matrix must be symmetric. This means $A=A^{T^{\prime}}.$
-  **Eigenvalues**: All the eigenvalues of a positive definite matrix are strictly positive.If $A$ is a positive definite matrix, then every eigenvalue $\lambda_i$ of $A$ satisfies $\lambda_i>0.$
-  **Positive Quadratic Form**: As already stated, for a matrix $A$ to be positive definite, the quadratic form $\mathbf{x}^TA\mathbf{x}$ must be positive for all non-zero vectors x. This ensures that the matrix is"stably" oriented in all directions in space.
-  **Cholesky Decomposition**: Every positive definite matrix can be decomposed into a product of a lower triangular matrix and its transpose (i.e., $A=LL^T$,where $L$ is a lower triangular matrix). This is known as the Cholesky decomposition, which is widely used in numerical methods and optimization.
-  **Invertible**: Positive definite matrices are always invertible because their eigenvalues are non-zero (since they are all positive). This means the determinant of a positive definite matrix is always greater than zero, i.e., $\det(A)>0.$
#### Testing
There are several methods to check if a matrix is positive definite:
1. **Quadratic Form Test**: For any non-zero vector $\mathbf{x}$,check if $\mathbf{x}^TA\mathbf{x}>0.$ This test can be impractical for large matrices, but it is the foundational definition of positive definiteness.
2. **Eigenvalue Test**: Compute the eigenvalues of the matrix $A$.If all the eigenvalues of $A$ are positive, then $A$ is positive definite.
3. **Leading Principal Minors Test (Sylvester's Criterion)**: A matrix $A$ is positive definite if and only if all the leading principal minors of $A$ are positive. The leading principal minors are the determinants of the upper-left $k\times k$ sub-matrices of $A$, for $k=1,2,\ldots,n$ .This is a practical way to check for positive definiteness, especially for small matrices.
4. **Cholesky Decomposition**: If a Cholesky decomposition of the matrix $A$ can be successfully performed, then $A$ is positive definite. If the matrix is not positive definite, the decomposition will fail.
## Similarity and Diagonalization
### Theorem: Eigenvalues and Diagonalization

If $A$ is diagonalizable, $A=PDP^{-1}$, where $D$ is a diagonal matrix with eigenvalues $\lambda_i$ on the diagonal. Suppose that $A$ have $n$ linearly independent eigenvectors, put them into column vectors of eigenvector matrix $P$, then we know the eigenvalues matrix can be obtained by $D=P^{-1}AP$. According to this point we know that $A^2$ has the same eigenvectors and squared eigenvalues with $A$. $A^{k}=PD^{k}P^{-1}$
##### Remark
- If eigenvalues are all different, then all the eigenvectors are independent. The eigenvector matrix will be invertible. Hence any matrix has no repeated eigenvalues is diagonalizable.
- Diagonalization is to find a coordinate (or a set of basis) such that a matrix $A$, which is a linear transform under standard coordinates, become a scaling-only transform under it. Also note that a diagonal matrix is a such transform (scaling only, no rotation).

What's more, if there is an invertible matrix $P$ such that $B=P^{-1}AP$, then **A is similar to B** $A\sim B$. Let $A$ and $B$ be $n \times n$ matrices with $A\sim B$. Then
- $\det A= \det B$
- $A$ is invertible if and only if $B$ is invertible.
- $A$ and $B$ have the same rank.
- $A$ and $B$ have the same characteristic polynomial.
- $A$ and $B$ have the same eigenvalues.
- $A^m\sim B^m$ for all integers $m > 0$.
- If $A$ is invertible, then $A^m\sim B^m$ for all integers $m$.
# Orthogonality
## Orthogonality in $\mathbb{R}^n$
### Definition
A set of vectors $\{v_{1},v_{2},\dots,v_{k}\}$ in $\mathbb{R}^n$ is an **orthogonal set** if all pairs of  vectors  are orthogonal, which means $v_{i}\cdot v_{j}=0,\quad i\neq j\ \text{for}\ i,j=1,2,\dots,k$. In orthogonal set, any vector in it are linearly
independent with each other. Furthermore, an **orthonormal**  basis is a orthogonal set with unit vectors, which can be a basis of subspace $W$ in $\mathbb{R}^n$.
### Orthogonal Matrix
The columns of an $m\times n$ matrix $Q$ form an orthonormal set if and only if $Q^TQ=I_{n}$. Such an $n\times n$ matrix $Q$ is an orthogonal matrix. A square matrix $Q$ is orthogonal if and only if $Q^{-1}=Q^T$. The following statements are equivalent:
- $Q$ is orthogonal matrix
- $||Qx||=||x||$ for every $x\in\mathbb{R}^n$
- $Qx\cdot Qy=x\cdot y$ for any $x,y\in \mathbb{R}^n$
Proof: Given $Q$ is orthogonal matrix.
1. $||Qx||=||x||$ for every $x\in\mathbb{R}^n$
The norm of $Qx$ is given by$$||Qx||=\sqrt{ (Qx)^T(Qx) }$$Furthermore, we know$$(Qx)^T(Qx)=x^TQ^TQx$$substitute that $Q^TQ=I$, we have$$x^TQ^TQx=x^TIx=x^Tx$$Thus we have$$||Qx||=\sqrt{ x^Tx }=||x||$$
2. $Qx\cdot Qy=x\cdot y$ for any $x,y\in \mathbb{R}^n$
$$Qx\cdot Qy=(Qx)^TQy=x^TQ^TQy=x^TIy=x^Ty=x\cdot y$$
According to $Q^{-1}=Q^T$, we know rows of $Q$ also form an orthogonal set.
### Properties of Orthogonal Matrix
1. $Q^{-1}$ is orthogonal.
2. $\det Q=\pm1$
3. If $\lambda$ is an eigenvalue of $Q$, then $\lambda=\pm 1$
4. If $Q_{1}$ and $Q_{2}$ are orthogonal $n\times n$ matrices, then so is $Q_{1}Q_{2}$.
## Orthogonal Complements and Orthogonal Projections
q### Orthogonal Complements
The orthogonal complements of a subspace $W$ contains **every** vector that is perpendicular to to $W$. This subspace is denoted by $W^{\perp}$.
We define the **orthogonal subspace** as $v^Tw=0\ \text{for all}\ v\in V\ \text{and}\ w\in W$. Firstly, according to $Ax=0$, we know that the null space $N(A)$ and the row space $C(A^T)$ are orthogonal subspaces. And the left bull space $N(A^T)$ and the column space $C(A)$ are orthogonal subspaces.
![[Pasted image 20241209091235.png|375]]
### Orthogonal Projections
Any vector can be decomposed into two parts like:
![[Pasted image 20241209102953.png|175]]
For an subspace $W=\text{span}\{u_{1},u_{2},\dots,u_{k}\}$, the orthogonal projection of vector $v$ in $\mathbb{R}^n$ onto $W$ is given by$$\text{proj}_{W}(\mathbf{v})=\sum_{i=1}^k\text{proj}_{u_{i}}(\mathbf{v})=\sum_{i=1}^k\left( \frac{u_{i}\cdot \mathbf{v}}{u_{i}\cdot u_{i}} \right)u_{i}$$The component of $v$ orthogonal to $W$ is the vector$$\text{perp}_{W}(\mathbf{v})=\mathbf{v}-\text{proj}_{W}\mathbf{v}$$
## The Gram-Schmidt Process and the QR Factorization
### The Gram-Schmidt Process
The **Gram-Schmidt process** is an algorithm for orthogonalizing a set of vectors in an inner product space, typically $\mathbb{R}^n$. The goal is to convert a set of linearly independent vectors into an orthogonal (or orthonormal) set of vectors while preserving the span of the original set. The process proceeds as follows:
1. **Input**: A set of linearly independent vectors ${v_1​,v_{2}​,…,v_{k}}$.
2. **Step 1**: Set $u_{1}=v_{1}$​, which will be the first vector in the orthogonal set.
3. **Step 2**: For each subsequent vector $v_{j}$​ (for $j=2,3,\dots,k$), subtract the projections of $v_j$​ onto the previously obtained orthogonal vectors:$$u_j = v_j - \sum_{i=1}^{j-1} \text{proj}_{u_i}(v_j)$$
4. **Step 3**: Normalize the vectors to make them orthonormal (if required):$$e_j = \frac{u_j}{\|u_j\|}$$
### QR Factorization
QR factorization decomposes a matrix into an orthogonal matrix and an upper triangular matrix such that:
- The columns of $Q$ form an orthonormal basis for the column space of $A.$
- The matrix $R$ contains the coefficients that transform the orthonormal basis into the original columns of $A$
the QR factorization expresses $A$ as $A=QR$. It's the Gram-Schmidt Process in nutshell.$$A=\begin{bmatrix}
\mathbf{a}&\mathbf{b}&\mathbf{c}
\end{bmatrix}=\begin{bmatrix}
q_{1}&q_{2}&q_{3}
\end{bmatrix}\begin{bmatrix}
q_{1}^Ta&q_{1}^Tb&q_{1}^Tc \\
0&q_{2}^Tb&q_{2}^Tc \\
0&0&q_{3}^Tc
\end{bmatrix}=QR$$
## Orthogonal Diagonalization of Symmetric Matrices
If $S$ is symmetric, that is, $S=S^T$, we have the **Spectral Theorem**: If $S$ is symmetric, it's diagonalizable with only real eigenvalues and orthogonal eigenvectors. Then symmetric diagonalization is given by$$S=PDP^{-1}=QXQ^T$$Note that Orthogonal Diagonalizable  $\Leftrightarrow$ Symmetric matrix. Also if $A$ is a symmetric matrix, then any two eigenvectors corresponding to distinct eigenvalues of $A$ are orthogonal.
By this property, we can calculate the projection form of spectral theorem$$S=QXQ^T=\sum_{{i=1}}^n\lambda_{i}q_{i}q_{i}^T$$