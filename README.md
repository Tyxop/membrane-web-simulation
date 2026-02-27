# Membrane Web Simulation

Interactive physics-based simulation of biological lipid membranes, built with [Three.js](https://threejs.org/).

## Demos

| File | Description |
|------|-------------|
| [bylayer.html](bylayer.html) | Full bilayer membrane with multi-species lipids, transmembrane proteins, cholesterol, and glycoproteins |
| [monolayer.html](monolayer.html) | Single-layer membrane simulation |
| [spherical.html](spherical.html) | Spherical membrane / vesicle simulation |
| [test1.html](test1.html) | Basic bilayer with proximity indicator |
| [test2.html](test2.html) | Multi-species membrane editor with live GUI |

## Features

- **Real-time physics** using Verlet integration
- **Multi-species lipids** with individual parameters (stiffness, elasticity, tail length, gravity)
- **Interactive mouse force field** — repulsion or attraction mode
- **Temperature control** — thermal vibration of lipid tails
- **Membrane elements** (bilayer version):
  - Transmembrane proteins
  - Peripheral proteins
  - Cholesterol
  - Glycoproteins with animated carbohydrate chains
- **High-performance rendering** with Three.js `InstancedMesh`
- **OrbitControls** for free 3D camera navigation

## Running

No build step required. Just open any `.html` file in a browser.

External dependencies are loaded via CDN:
- Three.js v0.160.0
- lil-gui v0.19

## Physics Overview

Each lipid molecule is a particle chain solved with distance constraints:
- **Head**: spherical particle held at target Y position by a spring
- **Tail**: segmented chain pulled by gravity, oriented with `lookAt()`
- **Mouse interaction**: raycasted force field within configurable radius

Key parameters (editable via the GUI panel):
| Parameter | Default | Effect |
|-----------|---------|--------|
| `spacing` | 0.95 | Grid spacing between lipids |
| `drag` | 0.93 | Velocity damping |
| `layerGap` | 2.5 | Distance from center to head layer |
| `segments` | 4 | Number of tail segments |
| `mouseForce` | 1.5 | Interaction force strength |
| `temperature` | — | Thermal noise amplitude |

## License

MIT
