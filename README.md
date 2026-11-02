# glow

A browser-based generator for soft, glowing gradient forms with glass and film-grain effects. Everything renders live in a WebGL shader and exports as a high-resolution PNG.

## Use it

Open `index.html` in a browser, or visit the GitHub Pages site for this repository.

- **New shape** (or the space bar) re-rolls the form and keeps your other settings.
- **Surprise me** randomises everything, including the palette and glass.
- Drag the image to move it and scroll to zoom.
- **Save PNG** exports at 2k or 4k on the long side.

## Controls

| Tab | What it does |
| --- | --- |
| Shape | Starting points (Comet, Horizon, Close-up), number of lobes, size, stretch and warp |
| Colour | Six palettes, six editable colour stops from rim to core, background colour, and light settings |
| Glass | Reeded, tiles, lenses, frosted or ripple glass, with strength, density, angle, highlights and dispersion |
| Grain | Film grain amount, size, colour noise, midtone weighting and live (animated) grain |
| Frame | Aspect ratio, zoom, rotation and slow drift animation |

## How it works

A single fragment shader sums up to five rotated Gaussian lobes, warps them with smooth noise, and maps the result through a six-stop colour ramp. A directional term shifts the colours across the form. The glass effects distort the sampling coordinates before the scene is drawn; dispersion samples the red and blue channels at offset positions. Grain is value noise scaled to the output size, so exports keep the texture you see in the preview.

No build step and no dependencies apart from the Inter Tight web font.

## Licence

MIT. See `LICENSE`.
