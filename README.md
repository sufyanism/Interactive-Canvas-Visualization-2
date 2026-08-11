# Interactive Canvas Visualization 2

A lightweight, dependency-free **HTML5 Canvas generative visualization engine** that creates animated geometric trails and particle patterns directly in the browser.

The project combines procedural motion, multiple geometric shape systems, fading trails, transparency, and additive compositing to create dynamic full-screen visual backgrounds.

## ✨ Features

- 12 distinct procedural visualization presets
- Full-screen responsive Canvas rendering
- Animated edge-based particle streamers
- Configurable particle count and trail length
- Multiple motion behaviours
- Rotating geometric shapes
- Fading particle trails
- Additive blending for glowing effects
- Random preset selection on page refresh
- Previous preset stored with `localStorage`
- No external JavaScript dependencies

## 🎨 Visualization Presets

| # | Preset | Visual Style |
|---|---|---|
| 01 | Wavy Flow Streams | Smooth sinusoidal trajectories |
| 02 | Laser Beam Lines | Straight glowing streams |
| 03 | Circuit Tech Traces | Angular zigzag paths |
| 04 | Orbital Arc Streams | Curved orbital motion |
| 05 | Dotted Particle Beams | Dotted particle trails |
| 06 | Floating Rhombus Diamonds | Rotating diamond outlines |
| 07 | Delta Vectors | Triangle-based particles |
| 08 | Hexagonal Mesh Cells | Rotating hexagonal outlines |
| 09 | Matrix Plus Nodes | Cross-shaped nodes |
| 10 | Pulsing Ring Rings | Circular particle trails |
| 11 | Helix Spiral Trajectories | Spiral motion patterns |
| 12 | Modular Pixel Blocks | Pixel-style particles |

## 🛠️ Technology

Built entirely with browser-native technologies:

- HTML5
- CSS3
- JavaScript
- Canvas 2D API
- `requestAnimationFrame`
- `localStorage`
- Canvas compositing

No npm packages, frameworks, bundlers, or backend services are required.

## 🚀 Getting Started

### Clone the repository

```bash
git clone https://github.com/sufyanism/Interactive-Canvas-Visualization-2.git
cd Interactive-Canvas-Visualization-2
```

### Run locally

You can open the HTML file directly in a modern browser.

For development, a local server is recommended:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## 📁 Project Structure

```text
Interactive-Canvas-Visualization-2/
│
├── Interactive Canvas Visualization-TapToChange.html
└── README.md
```

## ⚙️ How It Works

The engine creates animated `EdgeStreamer` objects. Each streamer enters from one of the four canvas edges and receives its own position, velocity, size, rotation, colour, lifetime, and trail history.

```text
           TOP
            ↓
            │
LEFT  →  CANVAS  ←  RIGHT
            │
            ↑
         BOTTOM
```

Each animation frame:

1. Stores the current position in the trail history.
2. Updates rotation and motion.
3. Applies the active preset's trajectory rules.
4. Draws the selected geometric shape.
5. Removes expired streamers.
6. Requests the next animation frame.

The animation loop uses:

```javascript
requestAnimationFrame(animate);
```

## 🎨 Rendering System

Different presets use different drawing techniques.

Line-based presets create continuous paths, while other presets render individual dots, diamonds, triangles, hexagons, crosses, rings, or pixels along the trail.

### Additive Glow

The glowing effect is created with Canvas additive compositing:

```javascript
ctx.globalCompositeOperation = 'lighter';
```

This allows overlapping particles and trails to produce brighter visual areas.

## 🔀 Random Preset Selection

The application selects a random visualization preset on each refresh while preventing the same preset from immediately repeating.

The last selected preset is stored in `localStorage`:

```text
zensical_shape_index
```

## 🎛️ Customization

The main configuration is:

```javascript
const SHAPE_PRESETS = [
    // presets
];
```

Each preset can control:

- Particle count
- Trail length
- Minimum speed
- Maximum speed
- Colour palette
- Shape type
- Motion behaviour

### Particle Count

```javascript
count: 180
```

Increase this value for denser visuals or decrease it for better performance.

### Trail Length

```javascript
trailLength: 45
```

Longer trails create smoother and more atmospheric effects.

### Speed

```javascript
speedMin: 0.9,
speedMax: 1.6
```

Increase these values to make the animation faster.

### Colours

```javascript
colors: [
    '#ffffff',
    '#fef08a',
    '#f59e0b',
    '#d97706',
    '#9a3412'
]
```

Replace these values to create your own colour theme.

## 🧩 Adding a New Shape

To create a new visualization:

1. Add a new preset to `SHAPE_PRESETS`.
2. Give it a unique `id`.
3. Define its count, trail length, speed, and colours.
4. Add its movement behaviour to `EdgeStreamer.update()`.
5. Add its rendering behaviour to `EdgeStreamer.draw()`.

This makes the engine easy to extend with new procedural shapes and animation systems.

## 📱 Responsive Behaviour

The Canvas automatically follows the browser viewport:

```javascript
width = canvas.width = window.innerWidth;
height = canvas.height = window.innerHeight;
```

The streamers are reinitialized whenever the window is resized.

## 💡 Use Cases

This project can be used for:

- Website hero backgrounds
- Documentation websites
- Landing pages
- Portfolio websites
- Generative art
- Creative coding experiments
- Digital installations
- Interactive visual effects
- Screensaver-style animations
- Abstract UI backgrounds

## ⚡ Performance

Performance depends primarily on:

- Number of streamers
- Trail length
- Shape complexity
- Canvas resolution
- Device hardware

For lower-powered devices, reduce:

```javascript
count
```

and:

```javascript
trailLength
```

For very large particle systems, WebGL or WebGPU would provide better GPU acceleration.

## 🔮 Future Improvements

Potential additions include:

- Mouse interaction
- Touch controls
- Live preset switching
- Speed controls
- Particle density controls
- Colour-palette editor
- Pause/resume controls
- Fullscreen mode
- PNG export
- SVG export
- Audio-reactive visualizations
- WebGL/WebGPU rendering
- GPU-accelerated particles
- Visual preset editor

## 🌐 Deployment

The project is suitable for static hosting:

- GitHub Pages
- Netlify
- Vercel
- Cloudflare Pages
- cPanel
- Apache
- Nginx
- Any static web server

No backend is required.

## 📜 License

Add a license to the repository according to how you want the project to be reused and distributed.

## 👨‍💻 Author

**Sufyan Mustafa**

GitHub: [@sufyanism](https://github.com/sufyanism)

## ⭐ Contributing

Ideas, new shape presets, performance improvements, and visual experiments are welcome.

If you create a new visualization preset, consider contributing it back to the project.

---

**Built with HTML5 Canvas, JavaScript, procedural motion, and generative graphics.**
