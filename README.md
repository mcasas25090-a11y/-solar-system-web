# Solar System

A responsive interactive Solar System made with HTML, CSS, JavaScript and Three.js. It includes a procedural starfield and planet surfaces, orbiting planets, Saturn's rings, touch and mouse camera controls, planet profiles, and animation controls.

## Run locally

Because the site uses ES modules, serve the files over HTTP rather than opening `file://`. No build step or backend is needed. For example, with Node.js installed:

```sh
npx serve .
```

Open the local URL printed by the server. Any static file server works; Python is not required.

## GitHub Pages

Commit `index.html`, `css/` and `js/` to your repository. In **Settings → Pages**, select the branch and `/ (root)` folder. Relative asset paths support project subpaths. Three.js and optional Google Fonts load from CDNs, so visitors need an internet connection.

## Controls

- Drag to rotate; scroll or pinch to zoom.
- Click a planet or use the planet shortcuts to view its profile.
- Use the play button, orbit toggle and speed slider to adjust animation.
- Select **Reset view** to restore the starting camera and Sun selection.
