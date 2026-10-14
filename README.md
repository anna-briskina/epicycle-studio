# Epicycle Studio

Watch spinning circles draw a shape. Epicycle Studio uses a Fourier series to break an outline into circles turning at whole-number speeds, then adds them one at a time until the shape takes form.

**[Open the live demo](https://anna-briskina.github.io/epicycle-studio/)**

## Features

- Six built-in shapes (heart, star, cat, fish, rocket, lightning), or draw your own
- Builds up from a single circle, adding one per lap so you can see each improvement
- Live equation panel with every term's radius, speed and starting angle
- One-click copy of the full equation for Desmos
- Light and dark themes

## How it works

The outline is sampled at 256 evenly spaced points and treated as a path in the complex plane. A discrete Fourier transform turns those points into coefficients, each one a circle with a radius, a rotation speed and a starting angle:

z(t) = Σ r_k · e^(i(n_k t + φ_k)),  0 ≤ t < 2π

The circles are chained tip to tail from largest to smallest, and the tip of the last one traces the shape.

## Run it locally

It's a single HTML file with no build step. Download `index.html` and open it in a browser.
