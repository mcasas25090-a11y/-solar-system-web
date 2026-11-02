# Solar System — Premium Simulator

An interactive Solar System explorer built with Three.js, HTML, CSS, and vanilla JavaScript. The site runs as a static project, includes an animated 2D view for browsers without WebGL2, and is designed to adapt from Android phones to desktop screens.

**GitHub Pages demo:** [mcasas25090-a11y.github.io/-solar-system-web](https://mcasas25090-a11y.github.io/-solar-system-web/)

## Features

- Three.js WebGL2 scene with three depth layers of stars, procedural nebulae, a distant spiral galaxy, and slowly drifting dust.
- Eight orbiting planets with 2K Solar System Scope map textures. Generated canvas maps remain in place if a remote map fails; maps are resized on smaller screens to limit GPU memory.
- Earth cloud and atmosphere layers, Venus cloud layer, Saturn's mapped rings, and Uranus's subtle rings.
- Glowing, rotating Sun with animated flare sprites and layered corona glow.
- 2,400 individually varied asteroids rendered in one instanced mesh between the Mars and Jupiter orbits.
- Kepler-style elliptical orbit animation and live telemetry for selected planet distance, orbital progress, heliocentric position, calculated orbital speed, elapsed simulation time, and simulation speed.
- Planet cards with diameter, mass, gravity, mean temperature, mean solar distance, orbital period, rotation period, major atmospheric components, and NASA-reported confirmed moon count.
- WebGL2 capability and context-loss handling. When 3D cannot run, an animated SVG Solar System retains planet selection, planet details, telemetry, pause/speed/orbit controls, and drag/pinch navigation.
- Responsive layout, smooth camera easing, pointer-based drag and pinch controls, pause/resume, orbit visibility, a 0–5× speed slider, and camera reset.

Planet and Sun textures load from the Solar System Scope public texture host. Internet access is required for Three.js, fonts, and high-resolution maps; procedural maps allow the scene to continue when an image request fails.

## Technologies

- HTML5 and CSS3
- Vanilla JavaScript ES modules
- Three.js r166.1 via jsDelivr CDN and an HTML import map
- SVG and Canvas 2D for generated visuals and the WebGL fallback

## Project structure

```text
.
├── index.html
├── css/
│   └── style.css
├── js/
│   └── main.js
└── README.md
```

## Install and run locally

No package installation or build step is required. Serve this directory over HTTP because the browser loads JavaScript modules. With Node.js installed, run:

```sh
npx serve .
```

Open the local address printed by the server. Any static HTTP server can be used; Python and a backend are not required.

## Controls

- Drag in the scene to rotate the camera; scroll or pinch to zoom. The 2D fallback supports drag-to-rotate and wheel/pinch zoom.
- Select a planet by clicking its visible globe or tapping a planet shortcut. The profile card and live telemetry update to that planet.
- Use the **play** button to pause or resume orbital motion and asteroid movement.
- Use **Orbits** to toggle the planetary orbit guides.
- Set simulation speed from **0× to 5×** in 0.1× steps.
- Use **Reset view** to ease the 3D camera back to its starting view and select the Sun.

## Mobile compatibility

The renderer uses WebGL2 with antialiasing disabled, a capped device pixel ratio, mobile-sized texture maps, instanced asteroids, and batched orbit lines. If WebGL2 is unavailable or the context is lost, the page switches to its SVG-based 2D simulator. Android Chrome requires an internet connection for the CDN modules and optional maps.

## Data and credits

Planetary diameters, masses, equatorial gravity, mean temperatures, mean Sun distances, orbital values, and confirmed moon counts are based on NASA's [Planetary Fact Sheet](https://nssdc.gsfc.nasa.gov/planetary/factsheet/) and its [definitions and notes](https://nssdc.gsfc.nasa.gov/planetary/factsheet/planetfact_notes.html). For giant planets, the fact sheet gives mean temperature at the 1-bar level. Moon counts are confirmed counts from that sheet and can change as new moons are confirmed. Atmospheric values are approximate major components; Mercury's is an exosphere.

Planet and Sun texture maps are provided by [Solar System Scope](https://www.solarsystemscope.com/textures/) under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license. The NASA references are used for factual data; generated nebulae, starfields, fallback maps, and SVG illustrations are created by the project.

## Verification note

The project has JavaScript syntax and Node-based checks for orbital calculations, fallback SVG generation, data coverage, and control event wiring. Rendering, visual layout, CDN CORS behavior, and touch performance still need testing in current desktop browsers and on Android Chrome.
