# Random Walk & Brownian Motion Visualisation

An interactive, browser-based simulation of random walks and Brownian motion. Watch stochastic processes unfold in real time, compare theoretical predictions against empirical results, and build intuition for the mathematics of diffusion.

### [Launch App](https://brendanjameslynskey.github.io/Random_Walk_Visualisation/)

---

## What is this?

A **random walk** is the simplest stochastic process: at each tick a particle takes a step in a random direction. Despite the simplicity of the rule, random walks are the backbone of an enormous range of science and mathematics. They were first studied seriously after Robert Brown observed the erratic jiggling of pollen grains suspended in water (1827). Nearly eighty years later, Einstein (1905) showed that this "Brownian motion" could be explained by molecular collisions, and in doing so provided some of the first compelling evidence for the atomic theory of matter. The rigorous mathematical framework was later completed by Norbert Wiener, giving us the **Wiener process** — the continuous-time, continuous-space limit of the discrete random walk.

The deep connection between random walks and physics lies in the **diffusion (heat) equation**:

> ∂u/∂t = D ∇²u

The probability density of a random walker's position satisfies exactly this equation, where the diffusion coefficient D is related to the step size δ and time step Δt by D = δ²/(2Δt). This means that the same PDE governing heat conduction in a metal bar also describes the statistical spread of a cloud of randomly walking particles. The signature result is that the root-mean-square (RMS) displacement grows as **√t**, not linearly — the famous "drunkard's walk" scaling. A drunk who takes random steps for four times as long only ends up, on average, twice as far from where they started.

Random walks and their generalisations appear across the sciences. **Geometric Brownian motion** is the standard model for stock prices (the basis of the Black-Scholes equation). In **polymer physics**, a long flexible chain in solution is well modelled by a self-avoiding random walk, connecting the walk's end-to-end distance to the polymer's radius of gyration. Ecologists model **animal foraging** as random searches; when resources are sparse, organisms often switch to **Lévy flights** — walks with heavy-tailed step-length distributions — which have been shown to be near-optimal search strategies. From the diffusion of molecules in a cell to the propagation of wildfires, the random walk is a lens through which disordered motion becomes mathematically tractable.

## Walk Types

| Type | Description |
|------|-------------|
| **1D Random Walk** | The classical discrete walk: at each step the particle moves +1 or −1 on a line with equal probability. Position vs time is plotted with a ±√(2Dt) diffusion envelope showing the theoretical standard-deviation boundary. The simplest model for understanding the √n scaling of displacement. |
| **2D Random Walk** | A lattice walk in four cardinal directions (up, down, left, right), each chosen with probability ¼. The X-Y path is drawn with a time-coloured gradient (blue → red) so you can see the walk's history. A √(4Dt) envelope circle shows the expected radial spread. |
| **1D Brownian Motion** | The continuous limit: steps are drawn from a Gaussian distribution with variance equal to the time step, approximating a true Wiener process. The resulting paths are continuous but nowhere differentiable — the hallmark fractal geometry of Brownian motion. |
| **2D Brownian Motion** | Two independent one-dimensional Brownian motions composed into a plane walk. The radial displacement follows a Rayleigh distribution, and the √(4Dt) envelope circle is overlaid for comparison. |
| **Lévy Flight** | Step lengths are drawn from a Cauchy (heavy-tailed) distribution, producing occasional dramatic long-range jumps interspersed with clusters of short steps. Unlike ordinary random walks, Lévy flights have infinite variance — the mean-square displacement diverges. These walks model phenomena from albatross foraging patterns to the distribution of banknote dispersal. |
| **Self-Avoiding Walk** | A lattice walk that never revisits a site. The walker picks a random unvisited neighbour at each step and halts if it becomes trapped. This is the standard model for polymer chains in a good solvent, where the chain's excluded-volume interaction prevents self-intersection. The end-to-end distance scales as n^ν, where ν ≈ 0.588 in 2D (larger than the ½ of an ordinary random walk). |

## Features

- **Six walk modes** — switch between 1D random walk, 2D random walk, 1D Brownian motion, 2D Brownian motion, Lévy flight, and self-avoiding walk via pill-style selector buttons
- **Multiple simultaneous walks** — run up to 20 walks at once, each drawn in a distinct colour from a 20-colour palette
- **Time-gradient colouring** — every walk path is coloured from blue (early steps) to red (late steps), with a Plotly colour bar, so temporal structure is immediately visible
- **Diffusion envelope overlays** — theoretical ±√(2Dt) boundaries (1D) or √(4Dt) radius circles (2D) are drawn as dashed green lines for direct comparison with the simulated paths
- **Displacement² vs time plot** — the mean ⟨r²⟩ across all walks is plotted alongside the theoretical linear prediction (2dDt, where d is the spatial dimension), demonstrating the diffusion law empirically
- **Final position histogram** — a histogram of final displacements (or final distances in 2D) is shown with a Gaussian overlay fitted to the data, illustrating the central limit theorem in action
- **Real-time statistics panel** — mean displacement, RMS displacement, max displacement, theoretical √n RMS, diffusion coefficient D, and walk count are updated live after every run
- **Heat equation display** — the connection ∂u/∂t = D∇²u is shown persistently beneath the statistics, reinforcing the link between the simulation and the underlying PDE
- **Step-by-step animation** — the "Animate" button plays walks frame by frame with adjustable speed (1–200), so you can watch the walk build up incrementally rather than seeing the final result instantly
- **Configurable parameters** — sliders for number of steps (10–10,000), number of simultaneous walks (1–20), step size (0.1–5.0), and animation speed
- **Start and end markers** — in 2D modes, green circles mark the origin and red crosses mark the final positions
- **Fully interactive Plotly.js charts** — zoom, pan, hover for coordinates, and export to PNG on every plot
- **Responsive dark-themed design** — a dark colour scheme (CSS custom properties) with gradient header, card-based layout, and a grid that collapses to single-column on narrow screens

## Built with

- [Plotly.js](https://plotly.com/javascript/) (v2.35.0) for interactive, publication-quality plotting
- Vanilla HTML, CSS, and JavaScript — no build tools, no frameworks, no dependencies beyond the Plotly CDN
- Hosted on [GitHub Pages](https://pages.github.com/)
