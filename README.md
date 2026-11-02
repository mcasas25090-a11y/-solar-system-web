# Solar System Simulator

A responsive, interactive Solar System simulator built with HTML, CSS, JavaScript and Three.js. It includes an animated WebGL2 scene, an animated 2D fallback, real-time orbital telemetry, planet profiles, a 2,400-instance asteroid belt, layered star/nebula/galaxy backgrounds, touch camera controls, animation controls and asynchronously loaded planet maps.

## Run locally

Because the site uses ES modules, serve the files over HTTP rather than opening `file://`. No build step or backend is required. For example, with Node.js installed:

```sh
npx serve .
```

Open the local URL printed by the server. Any static file server works; Python is not required.

## GitHub Pages

Commit `index.html`, `css/` and `js/` to your repository. In **Settings → Pages**, select the branch and `/ (root)` folder. Relative asset paths support project subpaths.

Three.js, planet textures and Google Fonts load from CDNs, so visitors need an internet connection. If a planet-map request fails, its procedural texture is kept. If WebGL2 is unavailable or its context is lost, the simulator switches to its animated 2D view.

## Controls

- Drag to rotate the 3D camera; scroll or pinch to zoom. In the 2D fallback, drag rotates the view and wheel or pinch zooms.
- Click a planet or use the planet shortcuts to view its profile and live orbit telemetry.
- Use the play button, orbit toggle and 0–5× speed slider to control the simulation.
- Select **Reset view** to restore the camera and Sun selection.

## Data and texture credits

Planet diameter, mass, surface gravity, mean temperature, mean solar distance, orbital velocity, and confirmed moon counts are based on NASA's [Planetary Fact Sheet](https://nssdc.gsfc.nasa.gov/planetary/factsheet/). Mean temperature for the giant planets refers to the one-bar level; confirmed moon counts can change as new moons are confirmed. Atmospheric compositions are approximate major components.

Planet and Sun texture maps are from [Solar System Scope](https://www.solarsystemscope.com/textures/), licensed under CC BY 4.0. The page links to that source; texture requests use its public download host and retain locally generated surfaces if a request fails.
