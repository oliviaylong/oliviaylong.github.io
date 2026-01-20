---
title: "Hamiltonian symmetries of quantum spin systems"
collection: studynotes
math: true
topic: Physics
date: 2026-01-20
toc: true
toc_sticky: true
categories: [Physics, Quantum]
excerpt: "Notes on Hamiltonian symmetries of quantum spin systems and a review of Pauli spin operator algebra. I also walk through the Jordan-Wigner transform."
---

One of the basic questions in physics is to ask what symmetries are present in a system and what does this tell us about the systems observables?

In this note, I review Pauli operator algebra and how using such relations can be used to check/find symmetries of quantum spin Hamiltonians.

A given Hamiltonian $H$ has a symmetry if it commutes with some symmetry transformation $S$. We can start with a simple system of 3 spins described by the following Hamiltonian:

$$H = -h \sum_{i \in {1, 2, 3}} \sigma_x + -J \sum_{\langle ij\rangle} \sigma_z^{(i)} \sigma_z^{(j)}$$

We can show that this Hamiltonian is symmetric under the transformation: $\hat{P}_x = \sigma_x^{(1)} \sigma_x^{(2)} \sigma_x^{(3)}$, which flips the spin of all 3 sites.

> $\sigma_x$ is a spin flip because: $$\sigma_x = \begin{matrix}
0 & 1 \\
1 & 0
\end{matrix} $$ thus $\sigma_x |\uparrow \rangle = |\downarrow \rangle$ and $\sigma_x |\downarrow \rangle = |\uparrow \rangle$

Let's first consider $P_x$ for a single site. We want to show that $[P_x, H] = 0$. 

Useful references:
