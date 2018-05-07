# 1 Probability and Statistics

1. (combinatorics)

Let $C(N,K) = 1$ for $K = 0$ or $K = N$, and $C(N,K) = C(N − 1,K) + C(N − 1,K − 1)$ for $N ≥ 1$.

Prove that $$C(N,K) = \frac{N!}{K!(N-1)!}$$ for $N ≥ 1$ and $0 ≤ K ≤ N$

Answer：

2. (counting)

> What is the probability of getting exactly 4 heads when flipping 10 fair coins?

Anwser：$C(n, k)p^{k}(1-p)^{n-k}=C(10, 4)(\frac{1}{2})^{4}(\frac{1}{2})^6$

> What is the probability of getting a full house (XXXYY) when randomly drawing 5 cards out of a deck of 52 cards?

Answer: $\frac{C(13, 1)C(12, 1)C(4,3)C(4,1)}{C(52,5)}$

3. (conditional probability)

> If your friend flipped a fair coin three times, and tell you that one of the tosses resulted in head, what is the probability that all three tosses resulted in heads?

Answer：$P(Y|X)=\frac{P(X, Y)}{P(X)}=\frac{0.5^3}{1-0.5^3}=\frac{1}{7}$

4. (Bayes theorem)

> A program selects a random integer $X$ like this: a random bit is first generated uniformly. If the bit is 0, $X$ is drawn uniformly from {0, 1, . . . , 7}; otherwise, $X$ is drawn uniformly from {0, −1, −2, −3}. If we get an $X$ from the program with $|X| = 1$, what is the probability that $X$ is negative?

Answer:  
$$
P(Y=0) = \frac{1}{2} \\
P(Y=1) = \frac{1}{2} \\
P(X= \pm1 | Y=0) = \frac{1}{8} \\
P(X= \pm1|Y=1) = \frac{1}{4} \\
P(X=\pm1) = P(X=\pm1, Y=1) + P(X=\pm1, Y=0) \\
=P(X=\pm1|Y=1)P(Y=1) + P(X=\pm1|Y=0)P(Y=0) \\
=\frac{1}{4} \times \frac{1}{2} + \frac{1}{8} \times \frac{1}{2} \\
= \frac{3}{16} \\
P(Y=1|X=\pm1) = \frac{P(Y=1,X=\pm1)}{P(X=\pm1)} \\
= \frac{P(X=\pm1|Y=1)P(Y=1)}{P(X=\pm1)} \\
=\frac{\frac{1}{4}\times \frac{1}{2}}{\frac{3}{16}} = \frac{2}{3}
$$

5. (union/intersection)

> If P(A) = 0.3 and P(B) = 0.4,
> what is the maximum possible value of P (A ∩ B)?
> what is the minimum possible value of P (A ∩ B)?
> what is the maximum possible value of P (A ∪ B)?
> what is the minimum possible value of P (A ∪ B)?

Answer: 0.3, 0, 0.7, 0.4



# 2 Linear Algebra

1.  (rank)

   > What is the rank of  

   $$
   \begin{bmatrix}
      1  & 2 & 1 \\
       1 & 0 & 3 \\
       1 & 1 & 2
   \end{bmatrix}
   $$

   Answer: 2. row reduction
   $$
   \begin{bmatrix}
      1  & 2 & 1 \\
       1 & 0 & 3 \\
       1 & 1 & 2
   \end{bmatrix} -> 

   \begin{bmatrix}
      1  & 2 & 1 \\
       1-1 & 0-2 & 3-1 \\
       1-1 & 1-2 & 2-1
   \end{bmatrix} ->
   \begin{bmatrix}
      1  & 2 & 1 \\
       0 & -2 & 2 \\
       0 & -1 & 1
   \end{bmatrix} ->
   \begin{bmatrix}
      1  & 2 & 1 \\
       0 & -2 & 2 \\
       0 & 0 & 0
   \end{bmatrix}
   $$

2. (inverse)

   > what is the inverse of 

   $$
   \begin{bmatrix}
      0  & 2 & 4 \\
       2 & 4 & 2 \\
       3 & 3 & 1
   \end{bmatrix}
   $$

   Answer: *Gauss-Jordan* 
   $$
   \begin{bmatrix}
      0  & 2 & 4 &| &1 &0 &0 \\
       2 & 4 & 2 &| &0 &1 &0 \\
       3 & 3 & 1 &| &0 &0 &1
   \end{bmatrix} -> \\

   \begin{bmatrix}
      0 - 5\times2+6\times3  & 0 & 0 &| &1 &-5 &6 \\
       2 & 4 & 2 &| &0 &1 &0 \\
       3 & 3 & 1 &| &0 &0 &1
   \end{bmatrix}  -> \\

   \begin{bmatrix}
      8 & 0 & 0 &| &1 &-5 &6 \\
       0 & 4+0.5\times0-2\times3 & 0 &| &0.5 &-1.5 &1 \\
       3 & 3 & 1 &| &0 &0 &1
   \end{bmatrix}  -> \\

   \begin{bmatrix}
      8 & 0 & 0 &| &1 &-5 &6 \\
       0 & -2 & 0 &| &0.5 &-1.5 &1 \\
       0 & 0 & 1- \frac{3}{8}\times0+\frac{-3}{2}\times0&| &\frac{3}{8} &\frac{-3}{8} &\frac{1}{4}
   \end{bmatrix}  -> \\

   \begin{bmatrix}
      1 & 0 & 0 &| &\frac{1}{8} &-\frac{5}{8} &\frac{3}{4} \\
       0 & 1 & 0 &| &-\frac{1}{4} &\frac{3}{4}&-\frac{1}{2} \\
       0 & 0 & 1&| &\frac{3}{8} &\frac{-3}{8} &\frac{1}{4}
   \end{bmatrix} 

   $$

3. (eigenvalues/eigenvectors)

   > What are the eigenvalues and eigenvectors of

   $$
   \begin{bmatrix}
      3  & 1 & 1 \\
       2 & 4 & 2 \\
       -1 & -1 & 1
   \end{bmatrix}
   $$

   Answer: 

   * To find the eigenvectors $v$, solve $det()$

4. (singular value decomposition)

   1. (a) For a real matrix $M$, let $M = UΣV^T$ be its singular value decomposition. Define $M^† = VΣ^†U^T$ ,

      where $Σ^†[i][j] = \frac{1}{Σ[i][j]}$ when$ Σ[i][j] $is nonzero, and 0 otherwise. Prove that $MM^†M = M$.

   2. (b) If M is invertible, prove that $M† = M^{−1}$.

5. (PD/PSD)

   A symmetric real matrix $A$ is positive definite (PD) *iff* $  x^{T}Ax > 0$ for all $ x\neq 0$, and positive semi-definite (PSD) if “>” is changed to “≥”. Prove:	

   1. (a) For any real matrix $Z$, $ZZ^T$ is PSD.
   2. (b) A symmetric A is PD *iff* all eigenvalues of A are strictly positive.

6. (inner product)

   Consider $x∈R^d$ and some $u∈R^d$ with$∥u∥=1$.

   1. What is the maximum value of $u^T x$? What $u$ results in the maximum value?
   2. What is the minimum value of $u^T x$? What $u$ results in the minimum value?
   3. What is the minimum value of $|u^T x|$? What $u$ results in the minimum value?



# 3. Calculus

1. (differential and partial differential)

   Let $f(x) = ln(1+e^{-2x})$.  What is $\frac{df(x)}{dx}$ ? Let $g(x, y)=e^x + e^{2y} +e^{3xy^2}$. What is $\frac{df(x)}{dx}$?

2. (chain rule)

   Let $f(x, y) = xy, x(u,v) = cos(u+v), y(u, v) = sin(u-v)$. What is $\frac{\partial f}{\partial v}$

3. (gradient and Hessian)

   Let $E(u,v)=(ue^v-2ve^{-u})^2$.  Calculate the gradient $\nabla E $  and the Hessian $\nabla^2 E$ at $u=1, v=1$

4. (Taylor’s expansion)

   Let $E(u,v)=(ue^v-2ve^{-u})^2$.  Write down the second-order Taylor’s expansion of $E$ around $u = 1$and $v = 1$.

5. (optimization)

   For some given$ A > 0,B > 0$, solve $\min_{\alpha} Ae^\alpha + Be^{-2\alpha}$

6. (vector calculus)

   Let **$w$** be a vector in $ R^d $and $E(w) = \frac{1}{2}w^{T}Aw+b^Tw$ for some symmetric matrix A and vector b. Prove that the gradient $\nabla E(w) = Aw + b$ and the Hessian $\nabla^2 E(w) = A$

