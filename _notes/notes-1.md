---
layout: archive
title: "Notes"
permalink: /notes/
author_profile: true
---

- - -

ADMM
======
**Background:** ADMM (Alternating Direction Method of Multipliers) was proposed 40 years ago and recently attracted lots of attention. The convergence of 2-block ADMM for convex problems was known; however, a recent paper in 2014 showed that multi-block ADMM can diverge even for solving a 3*3 linear system. Interestingly, if we randomly permuted the update order in each cycle (e.g. (132), (231),... compared to traditional cyclic order (123), (123),...), then the algorithm converges. The question is: why?  

**Our contribution:**  
1. Result. We show that for solving linear systems RP-ADMM (randomly permuted ADMM) converges in expectation for any number of blocks.  
2. High-level idea. One simple explanation for this phenomenon is "symmetrization'': the update matrix of cyclic ADMM is a non-symmetric matrix with complex eigenvalues, and random permutation partially symmetrize the update matrix to make the eigenvalues have a nicer distribution. In fact, the key result is that the eigenvalues of the update matrix of RP-CD (randomly permuted coordinate descent) lies in (-1/3, 1), a smaller region than that of cyclic CD which is(-1,1).  
3. Implications.  
   1. Problem level: RP-ADMM can potentially be a good solver for large-scale linearly constrained problems (LP, SDP, etc.)  
   2. Algorithm level: It was widely believed that RP rule is better than cyclic rule; however, little theory is established. This work provides one of the first theoretical results that RP rule is better than the cyclic rule.  
      * On the Expected Convergence of Randomly Permuted ADMM  Ruoyu Sun, Zhi-Quan Luo, Yinyu Ye.  

Matrix Completion
======
**--Updated 07/2016. Highlight the local geometry nature of our proof. New slides with a cleaner summary of the proof sketch.**  

**Background:** Motivated by applications such as recommender systems (e.g. Netflix prize),  the problem of recovering a low-rank matrix from a few observations has been popular recently. It is a prototype example of how to utilize the low-rank structure to deal with big data.  There are two popular approaches to impose the low-rank structure: nuclear norm based approach and matrix factorization (MF) based approach. The latter approach is especially amenable for big data problems, and has served as the basic component of most competing algorithms for Netflix prize. However, due to the non-convexity, it seems to be difficult to obtain a theoretical guarantee.  