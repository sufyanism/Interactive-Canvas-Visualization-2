# Interactive Canvas Visualization 2

A lightweight, dependency-free **HTML5 Canvas generative visualization engine** that creates animated geometric trails and particle patterns directly in the browser.

The project combines procedural motion, multiple geometric shape systems, fading trails, transparency, and additive compositing to create dynamic full-screen visual backgrounds.

## ✨ Features

- Full-screen responsive Canvas rendering
- Animated edge-based particle streamers
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
.. etc 

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


## About Me 
✨ I’m **Sufyan bin Uzayr**, an open-source developer passionate about building and sharing meaningful projects.
You can learn more about me and my work at [sufyanism.com](https://sufyanism.com/) or connect with me on [Linkedin](https://www.linkedin.com/in/sufyanism)

## Your all-in-one learning hub! 
🚀 Explore courses and resources in coding, tech, and development at **zeba.academy** and **code.zeba.academy**. Empower yourself with practical skills through curated tutorials, real-world projects, and hands-on experience. Level up your tech game today! 💻✨

**Zeba Academy**  is a learning platform dedicated to **coding**, **technology**, and **development**.  
➡ Visit our main site: [zeba.academy](https://zeba.academy)   </br>
➡ Explore hands-on courses and resources at: [code.zeba.academy](https://code.zeba.academy)   </br>
➡ Check out our YouTube for more tutorials: [zeba.academy](https://www.youtube.com/@zeba.academy)  </br>
➡ Follow us on Instagram: [zeba.academy](https://www.instagram.com/zeba.academy/)  </br>

**Thank you for visiting!**





