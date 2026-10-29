# Tornado Alley

[![Deploy to GitHub Pages](https://github.com/slayyyyer/tornado/actions/workflows/deploy-pages.yml/badge.svg)](https://github.com/slayyyyer/tornado/actions/workflows/deploy-pages.yml)

A real-time 3D tornado, built with [three.js](https://threejs.org/) in a single HTML file. No build step, no dependencies to install — just open it.

**Live demo:** https://slayyyyer.github.io/tornado/

## What's in the scene

Everything is generated procedurally at runtime:

- A green-tinted supercell sky and a grass field of instanced blades that bend in the wind
- A particle tornado funnel, brown with dirt at the base and grey dust higher up
- Debris (grass, wheat, dirt) and a ground dust cloud churning around the base
- A rotating wall cloud / mesocyclone above the funnel
- Distant rain and periodic lightning flashes

Drag to rotate, scroll to zoom; touch gestures work on mobile.

## Running locally

Open `index.html` in a browser. That's it. The only external request is three.js r128 from cdnjs, so you need an internet connection.

To serve it over HTTP instead:

```sh
python -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

Every push to `main` (or a manual **Run workflow**) publishes the site through the [deploy workflow](.github/workflows/deploy-pages.yml):

1. `index.html` is copied into a clean `_site/` directory
2. the artifact is uploaded with `actions/upload-pages-artifact`
3. `actions/deploy-pages` publishes it to the `github-pages` environment

The repository's Pages source must be set to **GitHub Actions** under *Settings → Pages → Build and deployment → Source*.
