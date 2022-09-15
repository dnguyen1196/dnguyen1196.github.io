---
layout: page
permalink: /publications/
title: Publications
description: Thanks for checking out my work!
nav: true
---

At a high level, **learning to rank** summarizes my research agenda. Specifically, I design, implement and analyze algorithms to identify the top items from user choice data, approval/disapproval responses, rankings, and from data that exhibit heterogeneity -- there are multiple underlying user subpopulations.

Towards this goal, my primary toolkit is **spectral algorithms**. Spectral algorithms learn low-dimensional representations of high-dimensional data (via eigendecomposition, SVD, low rank estimation, etc). They are attractive options for modern applications where high-dimensional data are abundant. Their analysis draws heavily from high dimensional statistics and matrix analysis.

Below are some of my works.

<br>

#### Efficient Top-K Recovery from Choice Data

<details>
<summary>Abstract</summary>
<br>
The intersection of learning to rank and choice modeling is an active area of research with applications in e-commerce, information retrieval and the social sciences. In some applications such as recommendation systems, the statistician is primarily interested in recovering the set of the top ranked items from a large pool of items as efficiently as possible using passively collected discrete choice data, i.e., the user picks one item from a set of multiple items. Motivated by this practical consideration, we propose the choice-based Borda count algorithm as a fast and accurate ranking algorithm for top K-recovery i.e., correctly identifying all of the top K items. We show that the choice-based Borda count algorithm has optimal sample complexity for top-K recovery under a broad class of random utility models. We prove that in the limit, the choice-based Borda count algorithm produces the same top-K estimate as the commonly used Maximum Likelihood Estimate method but the former's speed and simplicity brings considerable advantages in practice. Experiments on both synthetic and real datasets show that the counting algorithm is competitive with commonly used ranking algorithms in terms of accuracy while being several orders of magnitude faster.
</details>

<br>
Solo paper. Accepted to the Conference on Uncertainty in Artificial Intelligence (UAI 2022). [Arxiv](https://arxiv.org/abs/2206.11995).

<br>

#### A Spectral Approach to Item Response Theory

<details>
<summary>Abstract</summary>
<br>
The Rasch model is one of the most fundamental models in item response theory and has wide-ranging applications from education testing to recommendation systems. In a universe with $n$ users and $m$ items, the Rasch model assumes that the binary response $X_{li} \in \{0,1\}$ of a user $l$ with parameter $\theta^*_l$ to an item $i$ with parameter $\beta^*_i$ (e.g., a user likes a movie, a student correctly solves a problem) is distributed as $\Pr(X_{li}=1) = 1/(1 + \exp{-(\theta^*_l - \beta^*_i)})$. In this paper, we propose a \emph{new item estimation} algorithm for this celebrated model (i.e., to estimate $\beta^*$). The core of our algorithm is the computation of the stationary distribution of a Markov chain defined on an item-item graph. We complement our algorithmic contributions with finite-sample error guarantees, the first of their kind in the literature, showing that our algorithm is consistent and enjoys favorable optimality properties. We discuss practical modifications to accelerate and robustify the algorithm that practitioners can adopt. Experiments on synthetic and real-life datasets, ranging from small education testing datasets to large recommendation systems datasets show that our algorithm is scalable, accurate, and competitive with the most commonly used methods in the literature.
</details>

<br>
With [Anderson Y Zhang](http://www.andersonzhang.com/). Accepted to the Conference on Neural Information Processing (Neurips 2022).

<br>

#### Efficient and Accurate Learning of Mixtures of Plackett-Luce Models

<details>
<summary>Abstract</summary>
<br>
Mixture models of Plackett-Luce (PL) -- one of the most fundamental ranking models -- are an active research area of both theoretical and practical significance. Most previously proposed parameter estimation algorithms instantiate the EM algorithm, often with random initialization. However, such an initialization scheme may not yield a good initial estimate and the algorithms require multiple restarts, incurring a large time complexity. As for the EM procedure, while the E-step can be performed efficiently, maximizing the log-likelihood in the M-step is inefficient due to the combinatorial nature of the PL likelihood function (Gormley and Murphy 2008). Therefore, previous authors favor algorithms that maximize surrogate likelihood functions (Zhao et al. 2018, 2020). However, the final estimate may deviate from the true maximum likelihood estimate as a consequence. In this paper, we address these known limitations. We propose an initialization algorithm that can provide a provably accurate initial estimate and an EM algorithm that maximizes the true log-likelihood function efficiently. Experiments on both synthetic and real datasets show that our algorithm is competitive in terms of accuracy and speed to baseline algorithms.
</details>

<br>
With [Anderson Y Zhang](http://www.andersonzhang.com/). In submission.

<br>


#### Optimal and Private Learning from Human Response Data

<details>
<summary>Abstract</summary>
<br>
Item response theory is the study of human-centric decision models with diverse applications in psychological testing, education, recommendation systems among others. The Rasch model is one of the most fundamental models in item response theory and is still an object of active research. Despite its popularity and the human-centric nature of item response theory, two problems remain open in the Rasch model literature: analysis of the entrywise error bound for parameter estimation and privacy-preserving mechanisms. Recently, spectral methods have been shown to provide efficient and accurate parameter estimation under the Rasch model. In this work, we show that a spectral method can achieve the optimal entrywise error bound for individual parameter estimation. We also show that the spectral method is optimal in identifying the top-$K$ best item from response data, explaining the empirical success of the spectral method shown in our previous work. We propose, for the first time in the literature, a privacy preserving mechanism for item response theory, leveraging unique characteristics of the spectral algorithm. Our experiments show that our proposed mechanism preserves the privacy of the inviduals with little loss to parameter estimation accuracy.
</details>

<br>
With [Anderson Y Zhang](http://www.andersonzhang.com/). In progress.

<br>


***
## Manuscript and Technical Reports

#### Bayesian Active Drug Discovery

<details>
<summary>Abstract</summary>
<br>
We combine graph neural networks with Gaussian Process regression through deep graph kernel learning and demonstrate its robustness on quantitative structure-activity relationship (QSAR) modeling tasks. Equipped with such a model, a Bayesian optimization experiment on chemical space is conducted and compared against the time-stamped acquisition records of a real-world, time-sensitive molecular optimization mission: the identification of potent inhibitors of the main protease of SARS-CoV-2, the viral pathogen responsible for the COVID pandemic.
</details>

Publised at [ICML 2020's](https://realworldml.github.io/files/cr/48_BADD_paper_workshop.pdf) workshop on the applications of active learning.

<br>


#### Spectral Approaches to Ranking from Pairwise Comparisons
<details>
<summary>Abstract</summary>
<br>
Ranking from pairwise comparisons is a fundamental area in machine learning with diverse applications in recommendation systems, voting theory, information retrieval, etc. In recent years, a class of ranking algorithms based on spectral methods (Negahban et al. 2017, Chen et al 2019, Maystre and Grossglauser 2015, Agarwal et al. 2018) has received increased interest thanks to their good empirical performance, scalability and strong theoretical guarantees. In this paper, we will study in depth two such algorithms -- Rank Centrality (Negahban et al. 2017) and Iterative Luce Spectral Ranking (Maystre and Grossglauser 2015).
</details>

Ph.D. qualification deliverable.

<br>

#### Differentially Private Spectral Ranking
<details>
<summary>Abstract</summary>
<br>
Spectral ranking is a popular approach to rank aggregation, wherein the preferences or choices of several individuals are aggregated to produce an overall ranking of alternatives. However, in many applications -- including for example recommender systems and elections -- privacy of individuals' choice data is a key concern. Unfortunately, standard spectral ranking algorithms are not designed with this concern in mind. In this paper, we propose a simple fix: we suggest using a randomized response mechanism to collect individuals' choice data. By design, the resulting private spectral ranking algorithm achieves the strong guarantees of local differential privacy, which in turn also leads to a global differential privacy guarantee. We quantify the privacy-utility tradeoff of our algorithm under the popular multinomial logit (MNL) choice model -- which has also been used to analyze previous spectral ranking algorithms -- by deriving a sample complexity bound that makes the dependence on the privacy parameter explicit. Experiments on both synthetic and real data sets corroborate our analysis. 
</details>

MS. Thesis.

<br>