---
layout: single
title: Subgradients
permalink: writings/optimization/subgradients
author_profile: false
---

## Definition

The subgradient generalizes the gradient. For a convex function $f$, its subgradient at a point $x$ is:
$$ \partial f(x) = \{  v \,|\, f(x) + v^\top (y-x) \leq f(y) \} $$
It is the *set* of all *linear global under approximator* of the function $f(x)$. Clearly $ \nabla f(x) \in \partial f(x) $ (if the function is differentiable at $x$).

### Some facts about subgradients

1. The subgradient always exists for continuous convex function
<details>
<summary>Proof</summary>
TODO
</details>

2. If a convex function $f$ is differentiable at point $x$, $\partial f(x) = \{\nabla f(x)\}$.
<details><summary> Proof </summary>

</details>


## Subgradient optimization