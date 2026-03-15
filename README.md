# Random Walk & Brownian Motion Visualisation

[**Launch App**](https://brendanjameslynskey.github.io/Random_Walk_Visualisation/)

An interactive, browser-based visualisation of random walks and Brownian motion. Explore how simple stochastic rules give rise to diffusion, the central limit theorem, and the heat equation.

## The connection between random walks and diffusion

A random walk is a path formed by successive random steps. In the simplest 1D case a walker moves left or right with equal probability at each tick. As the number of steps grows and the step size shrinks, the discrete walk converges to **Brownian motion** — a continuous stochastic process first described by Robert Brown (1827) and formalised by Einstein (1905).

The probability density of the walker's position satisfies the **diffusion (heat) equation**:

> ∂u/∂t = D ∇²u

where D is the diffusion coefficient, related to the step size δ and time step Δt by D = δ²/(2Δt). This is the deep link between a particle's random jiggling and macroscopic heat conduction.

## Walk types

| Mode | Description |
|------|-------------|
| **1D Random Walk** | Discrete ±1 steps on a line. Position vs time and diffusion envelope ±√(2Dt). |
| **2D Random Walk** | Lattice walk in four cardinal directions. X-Y path with time-coloured gradient. |
| **1D Brownian Motion** | Continuous limit: Gaussian increments approximate true Brownian motion. |
| **2D Brownian Motion** | Two independent Brownian motions in x and y, with √(4Dt) envelope circle. |
| **Levy Flight** | Heavy-tailed (Cauchy-distributed) step sizes produce rare, dramatic long jumps. |
| **Self-Avoiding Walk** | Lattice walk that never revisits a site — a model for polymer chains. |

## Features

- **Multiple simultaneous walks** with distinct colours and time-gradient colouring (blue → red)
- **Diffusion envelope overlays** showing theoretical spread
- **Displacement² vs time** plot — linear growth demonstrates diffusion
- **Final position histogram** with Gaussian overlay (central limit theorem in action)
- **Real-time statistics**: mean displacement, RMS displacement, max displacement, theoretical √n scaling
- **Step-by-step animation** with adjustable speed
- **Fully interactive** Plotly.js charts (zoom, pan, hover)
- **Responsive** dark-themed design

## Built with

- [Plotly.js](https://plotly.com/javascript/) for interactive plotting
- Vanilla HTML, CSS, and JavaScript — no build step, no dependencies beyond the CDN
- Hosted on GitHub Pages
