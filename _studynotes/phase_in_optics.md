---
title: "Phase in Optics: Temporal vs. Spatial"
collection: studynotes
use_math: true
topic: Photonics
date: 2026-04-03
toc: true
toc_sticky: true
categories: [Photonics, Optics]
excerpt: "Notes on the concept of phase in optics, distinguishing between temporal phase (evolving in time) and spatial phase (evolving in space), and how they appear in interference, propagation, and coherence."
---

As a newcomer to optics, I remember being confused about which "phase" people were referring to in different contexts. I would say that it's an "overloaded function" (borrowing from the CS jargon).

Phase is one of the most important concepts in wave optics. It determines how waves interfere, how beams propagate, and how coherence is characterized. In this note, I distinguish between **temporal phase** and **spatial phase** and clarify many confusions of my younger self.

## The General Wave

A monochromatic plane wave can be written as:

$$E(\mathbf{r}, t) = E_0 \, e^{i(\mathbf{k} \cdot \mathbf{r} - \omega t + \phi_0)}$$

The total phase is:

$$\Phi(\mathbf{r}, t) = \mathbf{k} \cdot \mathbf{r} - \omega t + \phi_0$$

This contains both a **spatial** part ($$\mathbf{k} \cdot \mathbf{r}$$) and a **temporal** part ($$-\omega t$$), as well as a constant initial phase $$\phi_0$$.

---

## Temporal Phase

The **temporal phase** refers to how the phase evolves in time at a fixed point in space. At a fixed position $$\mathbf{r} = \mathbf{r}_0$$:

$$\Phi(t) = -\omega t + \text{const}$$

The rate of change of temporal phase is the **angular frequency**:

$$\frac{d\Phi}{dt} = -\omega$$

### Where temporal phase matters

**Interference between two frequencies:** If two waves with frequencies $$\omega_1$$ and $$\omega_2$$ are superposed, the intensity beats at the difference frequency $$\Delta \omega = \omega_1 - \omega_2$$. This beating is a purely temporal phase effect.

**Temporal coherence:** The coherence time $$\tau_c$$ characterizes how long a wave maintains a definite temporal phase relationship with itself. It is related to the spectral linewidth:

$$\tau_c \sim \frac{1}{\Delta\nu}$$

For a perfectly monochromatic source, $$\tau_c \to \infty$$.

**Phase modulation:** Electro-optic modulators impose a time-varying phase $$\phi(t)$$ on a beam, shifting its frequency spectrum.

---

## Spatial Phase

The **spatial phase** refers to how the phase varies across space at a fixed instant in time. For a wave propagating in the $$z$$-direction:

$$\Phi(z) = k z + \text{const}, \qquad k = \frac{2\pi}{\lambda} = \frac{\omega n}{c}$$

The rate of change of spatial phase along the propagation direction is the **wave number** $$k$$.

## Terminology in optics:

**Phase-matching** refers to **spatial** phase. In nonlinear optical processes (e.g., second-harmonic generation, sum-frequency generation, parametric down-conversion), multiple waves interact inside a medium. For efficient energy transfer between them, the spatial phases must add up coherently over the interaction length. This requires the wave vectors to satisfy a conservation condition.

For second-harmonic generation (SHG), a pump at frequency $$\omega$$ generates a signal at $$2\omega$$. The phase-matching condition is:

$$\Delta k = k_{2\omega} - 2k_\omega = 0$$

where $$k = \frac{\omega \, n(\omega)}{c}$$. If $$\Delta k \neq 0$$, the pump and generated wave fall out of step after a characteristic length called the **coherence length**:

$$L_c = \frac{\pi}{|\Delta k|}$$

Over distances much longer than $$L_c$$, the generated field oscillates rather than grows — the power cycles back and forth between the pump and signal.

**Why is phase-matching hard?** In a normally dispersive medium, $$n(2\omega) > n(\omega)$$, so $$k_{2\omega} \neq 2k_\omega$$ by default. Common strategies to achieve $$\Delta k = 0$$:

- **Birefringent phase-matching:** exploit the ordinary and extraordinary refractive indices of an anisotropic crystal (e.g., BBO, KTP). Tune the crystal angle so that $$n_e(2\omega) = n_o(\omega)$$.
- **Quasi-phase-matching (QPM):** periodically pole a ferroelectric crystal (e.g., PPLN) with period $$\Lambda = 2L_c$$, adding a reciprocal lattice vector $$G = 2\pi/\Lambda$$ to compensate $$\Delta k$$:

$$\Delta k' = k_{2\omega} - 2k_\omega - G \approx 0$$

QPM allows access to the largest nonlinear tensor elements and works in wavelength ranges where birefringent phase-matching fails.

### Wavefronts

A wavefront is a surface of constant spatial phase:

$$\mathbf{k} \cdot \mathbf{r} = \text{const}$$

- For a **plane wave**, wavefronts are flat planes perpendicular to $$\mathbf{k}$$.
- For a **Gaussian beam**, wavefronts are curved; the radius of curvature evolves with propagation distance.
- For a **spherical wave**, wavefronts are concentric spheres.

### Spatial coherence

Spatial coherence describes how correlated the phase is across the transverse extent of a beam at a given time. A spatially coherent beam has a well-defined wavefront; an incoherent source (e.g., a thermal lamp) has random phase fluctuations across its surface.

The **van Cittert–Zernike theorem** relates the spatial coherence of an incoherent source to the Fourier transform of its intensity distribution.

### Aberrations

Wavefront aberrations are spatially varying phase errors:

$$\Phi(\mathbf{r}_\perp) = \phi_\text{ideal}(\mathbf{r}_\perp) + \delta\phi(\mathbf{r}_\perp)$$

where $$\delta\phi$$ encodes the aberration (e.g., defocus, astigmatism, coma). Adaptive optics corrects $$\delta\phi$$ in real time.

---

## Connecting Temporal and Spatial Phase: Dispersion

In a dispersive medium, $$k$$ depends on $$\omega$$:

$$k(\omega) = \frac{\omega \, n(\omega)}{c}$$

A pulse (superposition of many frequencies) acquires **group delay** and **group delay dispersion** because different frequency components accumulate different temporal phases:

$$\phi(\omega) = k(\omega) \, L$$

Expanding around a central frequency $$\omega_0$$:

$$\phi(\omega) \approx \phi(\omega_0) + \phi'(\omega_0)(\omega - \omega_0) + \frac{1}{2}\phi''(\omega_0)(\omega - \omega_0)^2 + \cdots$$

- $$\phi'(\omega_0) = 1/v_g$$ gives the **group velocity**
- $$\phi''(\omega_0)$$ is the **group velocity dispersion (GVD)**, which stretches a pulse in time

---

## Quick Reference

| Quantity | Temporal Phase | Spatial Phase |
|---|---|---|
| Varies with | time $$t$$ | position $$\mathbf{r}$$ |
| Rate of change | $$\omega$$ (frequency) | $$k$$ (wave number) |
| Coherence concept | temporal coherence, $$\tau_c$$ | spatial coherence, $$l_c$$ |
| Interference effect | beats, frequency mixing | fringe patterns, diffraction |
| Practical example | mode-locking, AM/FM | lenses, holograms, aberrations |



