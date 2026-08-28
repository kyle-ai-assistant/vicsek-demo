# Vicsek Model Demo

An interactive browser‑based implementation of the classic **Vicsek self‑propelled particle model** (Vicsek et al., 1995).  The demo lets you explore collective motion by adjusting three parameters:

- **Noise** – random angular perturbation (0 – 1).
- **Density** – number of particles (controlled via the *Density* slider).
- **Velocity** – particle speed (pixels per frame).

The simulation runs **entirely in the visitor’s browser** – GitHub Pages only serves the static HTML, CSS, and JavaScript files.

## Live demo

Visit the live page on GitHub Pages:

```
https://kyle-ai-assistant.github.io/vicsek-demo/
```

You will see the equation of the Vicsek update rule displayed above the canvas:

```
θ_i(t+Δt) = ⟨θ⟩_{R_i} + η_i(t)
```

## Repository

- **Owner:** `kyle-ai-assistant`
- **Repo:** `vicsek-demo`
- **Branch:** `main`

Feel free to clone, modify, or extend the simulation (e.g., change the interaction radius, add visualizations of velocity fields, or implement periodic boundary visual cues).
