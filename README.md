# Vicsek Model Demo

An interactive browser‑based implementation of the classic **Vicsek self‑propelled particle model** (Vicsek et al., 1995).  The demo lets you explore collective motion by adjusting three parameters:

- **Noise** – random angular perturbation (0 – 1).
- **Density** – number of particles (controlled via the *Density* slider).
- **Velocity** – particle speed (pixels per frame).

The simulation runs **entirely in the visitor’s browser** – GitHub Pages only serves the static HTML, CSS, and JavaScript files.

## Live demo

*All equations shown for human readers are written in LaTeX and will be rendered by MathJax.*

Visit the live page on GitHub Pages:

```
https://kyle-ai-assistant.github.io/vicsek-demo/
```

You will see the equation of the Vicsek update rule displayed above the canvas (rendered with LaTeX):

$$\theta_i(t+\Delta t)=\langle\theta\rangle_{R_i}+\eta_i(t)$$

## Repository

- **Owner:** `kyle-ai-assistant`
- **Repo:** `vicsek-demo`
- **Branch:** `main`

## Model description

The Vicsek model describes a set of self‑propelled particles that try to align their direction of motion with their neighbours.  At each discrete time step the following operations are performed for **every particle**:

1. **Neighbour search** – all particles whose Euclidean distance is smaller than the **interaction radius \(R\)** are considered neighbours.  In our implementation we use
   ```
   const radius = 10; // interaction radius in canvas pixels
   ```
   so two particles influence each other if their toroidal distance satisfies \(\|\mathbf{r}_i-\mathbf{r}_j\| < 10\) pixels.
2. **Average heading** – the sine and cosine of the neighbours’ headings are summed and the average direction is obtained via \(\operatorname{atan2}\).
3. **Add noise** – a uniform random perturbation \(\eta_i(t)\) with amplitude set by the *Noise* slider is added to the average direction.
4. **Update heading** – the particle’s new heading becomes
   \[\theta_i(t+\Delta t)=\langle\theta\rangle_{\mathcal N_i}+\eta_i(t)\]
5. **Move particle** – the particle advances a distance \(v\) (the *Velocity* slider) in the new direction, applying periodic (toroidal) boundary conditions so that particles re‑enter the opposite side of the canvas.

These steps are implemented in the JavaScript functions `step()` (computes new angles) and `draw()` (renders the particles) and are called repeatedly via `requestAnimationFrame(loop)`.  The three sliders allow you to explore how noise, density, and velocity affect the emergence of collective motion.

## Repository

- **Owner:** `kyle-ai-assistant`
- **Repo:** `vicsek-demo`
- **Branch:** `main`


- **Owner:** `kyle-ai-assistant`
- **Repo:** `vicsek-demo`
- **Branch:** `main`

Feel free to clone, modify, or extend the simulation (e.g., change the interaction radius, add visualizations of velocity fields, or implement periodic boundary visual cues).
