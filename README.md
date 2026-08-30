# Vicsek Model Demo

A lightweight, browser‑based implementation of the classic **Vicsek self‑propelled particle model** (Vicsek et al., 1995). The demo visualizes collective motion of active particles and displays real‑time **energy** and **momentum** metrics, including the magnitude of the total momentum vector.

## Live demo

Visit the hosted page on GitHub Pages:

```
https://kyle-ai-assistant.github.io/vicsek-demo/
```

All equations are rendered with LaTeX via MathJax, so the update rule appears as:

$$\theta_i(t+\Delta t)=\langle\theta\rangle_{R_i}+\eta_i(t)$$

## How it works

- **Particles** are represented by objects `{x, y, angle}` stored in an array.
- **Neighbour search** uses a fixed interaction radius of 10 px with toroidal distance handling.
- **Update steps** per frame:
  1. Compute the average heading of neighbours.
  2. Add a uniform random noise term controlled by the **Noise** slider.
  3. Update each particle’s heading.
  4. Move the particle a distance `velocity` (set by the **Velocity** slider).
- **Metrics** calculated each step:
  - **Energy:** `0.5 * N * v²`
  - **Momentum vector:** `(Σ v·cosθ, Σ v·sinθ)`
  - **Momentum magnitude:** `√(Px² + Py²)`

These values are displayed in the control bar and update instantly as you adjust the sliders.

## Technical details

- **Stack:** Pure HTML5, CSS, and vanilla JavaScript. No build toolchain required.
- **Dependencies:** MathJax CDN for LaTeX rendering.
- **Deployment:** Static files served via GitHub Pages.
- **Extensibility:** Developers can easily add new controls (e.g., interaction radius), visual enhancements (particle trails), or a CI workflow for linting and headless testing.

## Repository

- **Owner:** `kyle-ai-assistant`
- **Repo:** `vicsek-demo`
- **Default branch:** `main`

Feel free to clone, modify, or extend the simulation for research, teaching, or hobby projects.
