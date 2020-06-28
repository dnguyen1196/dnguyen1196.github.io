---
layout: single
title: Subgradients
permalink: writings/optimization/subgradients
author_profile: false
---

## Definition

The subgradient (also called subdifferential) generalizes the gradient. For a convex function $f$, its subgradient at a point $x$ is:

$$ \partial f(x) = \{  g \,|\, f(x) + g^\top (y-x) \leq f(y) \,\,\forall y \in \mathbf{dom}f \} $$

It is the *set* of all *linear global under approximator* of the function $f(x)$. Clearly $ \nabla f(x) \in \partial f(x) $ (if the function is differentiable at $x$).

### Some facts about subgradients


**1. If $x \in \mathbf{int} \,\mathbf{dom} \, f$ then $\partial f(x)$ is non-empty, closed convex and compact**
<details>
<summary>Proof</summary>
Note the definition of the subgradient. Suppose we fix a $ y $, define $\partial f(x)_y = \{ g \,|\, f(x) + g^\top (y-x) \leq f(y) \}$. This set is a hyperplane, which is closed and convex. Then:
$$ \partial f(x) = \cap_y \partial f(x)_y $$
Is the intersection of (potentially infinite number of) hyperplanes, therefore remains closed and convex.
<br>
<br>
To prove that $\partial f(x)$ is non-empty. We use the concept of supporting hyperplane and epigraph. Graphically, we can guess that a subgradient is also a supporting hyperplane for the epigraph of $f$ at point $x$. The proof uses the fact that the epigraph of any convex function is also convex to state that a supporting hyperplane exists. It then follows, after some algebraic manipulations, that the subgradient set is non-empty.
<br>
<br>
Note that if the domain of $f$ is $\mathbb{R}^n$ then a point in $\mathbf{epi} \,f$ is in $\mathbb{R}^{n+1}$. A point $(y, t) \in \mathbf{epi}\, f$ if and only if $f(y) \leq t$. 
<br>
<br>
Now, the epigraph of a convex function is a convex set. Now, suppose we pick a point $x$, $(x, f(x))$ is on the *boundary* of this convex set. We can use the supporting hyperplane theorem to conclude that there exist a vector $a \in \mathbb{R}^n$ and a scalar $b$ such that:

$$ \begin{bmatrix}a \\b \end{bmatrix}^\top \begin{bmatrix}y\\ t \end{bmatrix} \leq \begin{bmatrix}a \\b \end{bmatrix}^\top \begin{bmatrix}x\\ f(x) \end{bmatrix} $$
For all $(y,t) \in \mathbf{epi} \, f$. Rearranging the above inequality gives:
$$  a^\top (y-x) \leq b(f(x)-t) $$

Here we note that, if $y=x$, then the left hand side is $0$ while $f(x) = f(y) \leq t$. Therefore, $b \leq 0$. Dividing both sides of the above inequality by $b$ gives us:

$$ \frac{1}{b}a^\top (y-x) \geq f(x) - t $$

Recall that this holds for all $(y, t) \in\mathbf{epi}\, f$, which means it holds for $t = f(y)$. Another round of rearranging gives:
$$ f(y) \geq f(x) - \frac{1}{b}a^\top (y-x) $$
Thus $\frac{-1}{b}a \in \partial f(x)$

<br>
<br>
**TODO**: proof of compactness

</details>

<br />

**2. The subgradient can also be written as:**
   $$ \partial f(x) = \{ g \,|\, g^\top v \leq f_v'(x) \,\, \forall v \} $$

<details>
<summary>Proof</summary>
Let $S = \{ g \,|\, g^\top v \leq f_v'(x) \,\, \forall v \}$, we want to prove that $g \in S$ if and only if $g \in \partial f(x)$. For the forward direction, suppose $g \in S$, then for any $v$:
$$ g^\top v \leq f'_v(x) $$
Let $v = \frac{1}{t}(y-x)$ for some $y$ and $t > 0$ (so any $v$ can be written in this way). We see that:
$$ \lim_{t\rightarrow 0} g^\top \frac{y-x}{t} \leq \lim_{t\rightarrow 0} \frac{f(x+tv)-f(x)}{t} = \frac{f(x+ t\frac{y-x}{t})-f(x)}{t} $$ 
$$= \frac{f(y)-f(x)}{t}$$
By monotonicity of limits, we have:
$$ g^\top (y-x) \leq f(y)-f(x) $$

<br/>
For the reverse direction, suppose now that $g \in \partial f(x)$, or $f(y) \geq f(x) + g^\top (y-x)$. Some rearrangment gives:
$$ g^\top (y-x) \leq f(y)-f(x) $$
This inequality holds for all $y$. Now let $y-x = tv$ for some $v$ and $t > 0$. We have:
$$ g^\top tv \leq f(x+tv)-f(x)$$
Dividing both sides by $t$ and since this inequality holds for any $t > 0$, it holds for $t \rightarrow 0$.

</details>

<br />

**3. The directional derivative can be written as:**
$$ f'_v(x) = \sup_{g \in \partial f(x)} g^\top v $$

<details>
<summary>Proof</summary>
</details>

<br />

**4. If a convex function $f$ is differentiable at point $x$, the subgradient is a singleton set: $$\partial f(x) = \{ \nabla f(x) \}$$**
<details><summary> Proof </summary>
TODO
</details>


## Subgradient optimization


## Stochastic subgradient optimization


## Useful notes

[Notes on Hyperplane Separating Theorem](http://www.ifp.illinois.edu/~angelia/L7_separationthms.pdf)