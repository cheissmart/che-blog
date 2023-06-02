---
layout: post
title:  "Quadratic forms and positive definite matrix"
date:  2023-06-02 14:32:00 +0800
categories: math
tags: [calculus, matrix, linear algebra]
image: bowling.jpg
---
## Intro
Consider the following problem:

Given $Q(\textbf{x}) = Q(x_1, x_2, x_3) = 3 x_1 ^ 2 + 2 x_2 ^ 2 + 1 x_3 ^ 2 + 4 x_1 x_2 + 4 x_2 x_3$

1. Is $Q(x_1, x_2, x_3) > 0$ for all $$\textbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} \neq 0$$ ?
2. What is the maximum possible value of $Q(x_1, x_2, x_3)$ given the constrant that $x_1 ^ 2 + x_2 ^ 2 + x_3 ^ 2 = 1$ ?

## What is quadratic form?
The $Q(\textbf{x}) = Q(x_1, x_2, x_3)$ defined above is an example of a **quadratic form**. Formally, a **quadriatic form** on $\mathbb{R}^n$ is an expression of the form 
<center>
	$$Q(\textbf{x}) = \textbf{x}^{\intercal}A\textbf{x} = \sum_{1 \leq i, j \leq n}{A_{i, j}x_i x_j}$$ where $A$ is a $n$ by $n$ matrix.
</center>
Note that 
<center>
	$$
	Q(\textbf{x}) = \frac{1}{2} \sum_{1 \leq i, j \leq n}{(A_{i, j} + A_{j, i})x_i x_j}
	$$
</center>
So if there is another matrix $B$ such that 
<center>
	$A_{i, j} + A_{j, i} = B_{i, j} + B_{j, i}, \forall 1 \leq i, j \leq n$
</center>
then
<center>
	$\textbf{x}^{\intercal}A\textbf{x} = \textbf{x}^{\intercal}B\textbf{x}, \forall \textbf{x} \in \mathbb{R}^n$
</center>
We can always find a symmetric matrix with this property by letting
<center>
	$B_{i, j} = \frac{1}{2}(A_{i, j} + A_{j, i})$
</center> 
The matrix $B$ defined this way is called the **associated symmetric matrix** of the quadratic form. 

The nice thing about having a symmetric matrix is that we can apply **spectral decomposition**:
<center>
	$B = U\Lambda U^{\intercal}$
</center>
where $\Lambda$ is a **diagonal** matrix consisting of the eigenvalues ($\lambda_1, \lambda_2, ..., \lambda_n$) and $U$ is an **orthonormal matrix** (I usually write $Q$ for an orthonormal matrix, but I have already used it for the quadratic form). So we can now rewrite
<center>
$$
\begin{aligned}
	Q(\textbf{x}) &= \textbf{x}^{\intercal}B\textbf{x} \\
				  &= \textbf{x}^{\intercal}U\Lambda U^{\intercal}\textbf{x} \\
				  &= (U^{\intercal}\textbf{x})^{\intercal}\Lambda (U^{\intercal}\textbf{x}) \\
				  &= \textbf{y}^{\intercal}\Lambda\textbf{y},\space \textbf{y} = U^{\intercal}\textbf{x} \\
				  &= \sum_{i = 1}^n {\lambda_i y_i^2}
\end{aligned}
$$
</center>

## Definiteness of a matrix
Now, we can answer the first question raised in the Intro.

We can write $Q(\textbf{x}) = \sum_{i = 1}^n {\lambda_i y_i^2}$ where $\textbf{y} = U^{\intercal}\textbf{x}$. Since $U^{\intercal}$ is invertible (because $U$ is orthonormal), for any $\textbf{y}\in\mathbb{R}^n$, there exists $\textbf{x} \in \mathbb{R}^n$ such that $\textbf{y} = U^{\intercal}\textbf{x}$. Moveover, $\textbf{x} = 0 \iff \textbf{y} = 0$. Therefore, 
<center>
$$
\begin{aligned}
	Q(\textbf{x}) > 0, \forall \textbf{x} \in \mathbb{R}^n, \textbf{x} \neq 0 &\iff \sum_{i = 1}^n {\lambda_i y_i^2}, \forall \textbf{y} \in \mathbb{R}^n, \textbf{y} \neq 0\\
	& \iff \lambda_i > 0, \forall i \in \{1, 2, ..., n\}
\end{aligned}
$$
</center>	

In other words, we only have to check if all eigenvalue of the **associated symmetric matrix** $B$ are positive.\\
In this case $$B = \begin{bmatrix} 3 & 2 & 0 \\ 2 & 2 & 2 \\ 0 & 2 & 1 \end{bmatrix}$$ and its eigenvalues are $5, 2, -1$. Thus, we can conclude that the statement "$Q(x_1, x_2, x_3) > 0$ for all $$\textbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} \neq 0$$" is false. In fact, we can construct a $\textbf{x}$ such that $Q(\textbf{x}) < 0$ if we calculate the $U$ matrix(eigenvactors of $B$), but I will leave it as an exercise for the reader.

### Some definitions
It turns out that the question discussed above is related to the notion of "definiteness" of a matrix. Here we introduce some definitions:
<div class='yellow-warning'>
Let $A$ be a <b>symmetric </b> $n$ by $n$ square matrix. $A$ is <br/>
<ul>
  <li><b>Positive definite</b> if $\textbf{x}^{\intercal}A\textbf{x} > 0$ for all $\textbf{x}\neq0$</li>
  <li><b>Negative definite</b> if $\textbf{x}^{\intercal}A\textbf{x} < 0$ for all $\textbf{x}\neq0$</li>
  <li><b>Indefinite</b> if $\textbf{x}^{\intercal}A\textbf{x}$ takes both positive and negative values</li>
  <li><b>Positive semidefinite</b> if $\textbf{x}^{\intercal}A\textbf{x} \geq 0$ for all $\textbf{x}\neq0$</li>
  <li><b>Negative semidefinite</b> if $\textbf{x}^{\intercal}A\textbf{x} \leq 0$ for all $\textbf{x}\neq0$</li>
</ul>
</div>
With arguments similar to the above, we can see that:
<div class='yellow-warning'>
Let $A$ be a <b>symmetric </b> $n$ by $n$ square matrix. $A$ is <br/>
<ul>
  <li><b>Positive definite</b> if all eigenvalues are positive</li>
  <li><b>Negative definite</b> if all eigenvalues are negative</li>
  <li><b>Indefinite</b> if $A$ has both positive and negative engenvalues</li>
  <li><b>Positive semidefinite</b> if all eigenvalues are non-negative</li>
  <li><b>Negative semidefinite</b> if all eigenvalues are non-positive</li>
</ul>
</div>
The notion of positive definite is useful when optimizing multivariate functions because it is related to the curvature of a function. More specifically, it is used in the **second partial derivative test**.

> **Theorem (Second partial derivative test)**. Suppose $f:\mathbb{R}^n \rightarrow \mathbb{R}$ is a differentiable real function whose second partial derivatives exist and are continuous. The Hessian matrix $H$ of $f$ is defined as $H_{i, j}(\textbf{x}) = \frac{\partial^2f}{\partial_{x_i}\partial_{x_j}}(\textbf{x}) \in \mathbb{R}^{n\times n}$. Since the second partial derivatives are continuous, by Schwarz's theorem, $H$ is symmetric.
>
> Suppose that $\nabla f(a) = 0, a \in \mathbb{R}^n$:
> 1. If $H$ is *positive definite* at $a$, then $f$ attains a local minimum at $a$.
> 2. If $H$ is *negative definite* at $a$, then $f$ attains a local maximum at $a$.
> 3. If $H$ is *indefinite* at $a$, then $a$ is a saddle point for $f$ (i.e. not local maximum and not local minimum).
> 4. Otherwise, the test is inconclusive.

## Maximizing and Minimizing Quadratic Forms
Now, we consider the second question.

We are trying to maximize $Q(\textbf{x})$ under the constraint that $\lVert\textbf{x}\lVert = 1$.
Recall that we can write $Q(\textbf{x}) = \textbf{y}^{\intercal}\Lambda \textbf{y}$, $\textbf{y} = U^{\intercal}\textbf{x}$. \\
Since $U$ is orthonormal, not only is the mapping between $y$ and $x$ bijective but also **length-preserving** (i.e. $\lVert\textbf{y}\lVert = \lVert\textbf{x}\lVert$). \\
Therefore, maximizing $Q(\textbf{x})$ under the constraint that $\lVert\textbf{x}\lVert = 1$ is equivalent to maximizing $\textbf{y}^{\intercal}\Lambda \textbf{y} = \sum_{i = 1}^n {\lambda_i y_i^2}$ under the constraint that $\lVert\textbf{y}\lVert = \sum_{i = 1}^n {y_i^2} = 1$.\\
Suppose that $U$ and $\Lambda$ are picked in such a way that $\lambda_1, \lambda_2, ..., \lambda_n$ are in descending order. Then letting $\textbf{y}=\begin{bmatrix}1&0&...&0\end{bmatrix}^{\intercal}$ attains maximum, and $\textbf{y}=\begin{bmatrix}0&...&0&1\end{bmatrix}^{\intercal}$ attains minimum (this should be fairly obvious). \\
Moreover, the maximum value is $\lambda_1=\lambda_{\max}$, and minimum is $\lambda_n=\lambda_{\min}$.
We can also recover $$\textbf{x}_{\max} = U \textbf{y}_{\max} = \textbf{u}_1$$, $$\textbf{x}_{\min} = U\textbf{y}_{\min} = \textbf{u}_n$$.
## Postcard
<div class = "postcard">
	<p>
	I am watching the <a href="https://www.youtube.com/playlist?list=PLoCMsyE1cvdV4CkdIZRKW8lk2BBOW-fbF" target="_blank">Introduction to Automata and Complexity Theory</a> lecture series recently.<br/><br/>
	Here is an interesting <a href="https://codeforces.com/gym/104345/problem/A" target="_blank">problem</a> I saw recently.<br/><br/>
	Songs for today: <a href="https://www.youtube.com/watch?v=SiUznAY1wq8" target="_blank">612星球</a>, <a href="https://www.youtube.com/watch?v=NFtChxqNPvw" target="_blank">真的假的</a>
	</p>
	<div style="height: 100%; position: relative; font-size: 10px;"> <span style="position: absolute; bottom: 0; right: 0; color: #888888"> <a style="color: #888888" href="https://www.freepik.com/free-vector/stamped-postcard-frame-with-travel-theme_13311480.htm#query=travel%20postcard&position=2&from_view=keyword">Image by rawpixel.com</a> on Freepik </span> </div>
</div>
