# System Breach: Love Detected 💖

A retro-style terminal animation that transforms into a stunning Valentine's Day surprise with realistic rose petals, sparkle effects, and an animated heartbeat cursor.

## ✨ Features

### 🖥️ Terminal Sequence
- **Retro Hacking Aesthetic**: Green-on-black terminal with VT323 monospace font
- **Authentic Typing Animation**: Character-by-character typing with random delays
- **System Boot Sequence**: Custom boot messages (`romance_protocol`, `shared_memories.dat`, etc.)
- **Error Alert**: Blinking red "SYSTEM OVERLOAD: TOO MUCH LOVE DETECTED" warning
- **Responsive Text**: Font sizes automatically adjust for mobile and desktop

### 🌹 Rose Petal Animation
- **Realistic Falling Petals**: Organic bezier curve shapes with gradient fills for depth
- **3D Tilt Simulation**: Dynamic x-axis scaling creates realistic rotation effect
- **Gentle Swaying**: Sinusoidal motion mimics natural petal floating
- **Color Variety**: 8 different petal colors (pinks, reds, whites, mauves)
- **Mouse Repulsion**: Petals gently push away from cursor interaction
- **Size Scaling**: Petals automatically resize for mobile devices (50% on phones, 70% on tablets)

### ✨ Sparkle Effects
- **Collision Detection**: Sparkles burst when petals pass through the heart zone
- **Star-Shaped Glints**: Cross-pattern sparkles with glow effects
- **Physics-Based Movement**: Sparkles drift with velocity decay
- **Color Variation**: Alternating pink and white sparkle colors
- **Fade Out Animation**: Smooth alpha decay over time

### 💖 Interactive Spotlight (Desktop Only)
- **Dark Room Effect**: Screen goes pitch black after terminal sequence
- **Mouse Flashlight**: Follow the mouse to find the hidden heart and message
- **Realistic Beam**: Soft yellow glow with falloff gradient
- **Floating Dust Particles**: Visible only in the spotlight beam
- **Click to Expand**: Spotlight expands and fades to reveal full scene

### 🖱️ Animated Cursor (Desktop Only)
- **Realistic Heartbeat**: "Lub-dub" rhythm with two quick beats and a pause
- **Dynamic Glow**: Shadow bloom intensifies with each heartbeat pulse
- **Heart Trail**: Fading mini hearts trail behind mouse movement in varying pink hues
- **Orbiting Sparkles**: 3 tiny dots orbit the cursor at different speeds
- **Soft Aura**: Breathing pink glow ring around the cursor
- **3D Depth**: Inner highlight creates dimensional effect

### 📱 Mobile Optimization
- **Touch Device Detection**: Automatically detects tablets and mobile devices
- **Cursor Hiding**: Custom cursor and spotlight disabled on touch devices
- **Responsive Scaling**: Heart and text scale appropriately for small screens
- **Auto-Reveal**: Skips spotlight phase on mobile, goes directly to final animation
- **Smaller Petals**: Petal size scales down on portrait and small screens
- **Optimized Spacing**: Tighter line spacing and gaps on mobile portrait mode

### 🎨 Particle Heart Animation
- **Particle Formation**: Heart shape constructed from hundreds of particles
- **Edge Spawning**: Particles fly in from all four screen edges
- **Easing Motion**: Smooth ease-in animation to target positions
- **Jitter Effect**: Subtle continuous jitter for organic feel
- **Text from Pixels**: "HAPPY VALENTINES DAY" and "My Love" rendered as particle text
- **Vertical Centering**: Entire composition (heart + text) calculated to fit viewport with padding

## 🚀 How to Run

Simply open `index.html` in any modern web browser. No build process or dependencies required.

**Live Demo**: [Your GitHub Pages URL]

## 🛠️ Customization

Edit the `CONFIG` object at the top of the `<script>` section in `index.html`:

```javascript
const CONFIG = {
    targetName: "My Love",              // Name displayed below the heart
    customMessage: "HAPPY VALENTINES DAY", // Main message text
    bootLines: [                         // Terminal boot sequence
        "> Initializing romance_protocol...",
        "> Loading shared_memories.dat...",
        "> Connecting to heart_module...",
        "> Bypassing emotional_firewalls...",
        "> analyzing_compatibility.exe...",
        "> ACCESS GRANTED."
    ],
    colors: {
        background: "#000000",           // Background color
        text: "#0f0",                    // Terminal text color (green)
        heart: "#ff3366",                // Main heart color
        petals: [/* array of 8 pink/red colors */] // Rose petal colors
    }
};
```

### Advanced Customization

**Petal Behavior** (lines 330-360):
- `this.size`: Petal size range
- `this.speed`: Fall speed
- `this.swayAmplitude`: How much petals sway side-to-side
- `this.curlFactor`: Petal shape variation

**Sparkle Settings** (lines 285-325):
- Number of sparkles per collision: Change loop count in line 390
- Sparkle lifespan: Adjust `this.decay` value

**Cursor Animation** (`animateCursor` function):
- Heartbeat speed: Change time multiplier in `beatCycle` calculation
- Trail length: Adjust `cursorTrail` max length (line 254)
- Orbit speed: Modify time multipliers in orbiting sparkle loop

## 💻 Technologies

- **HTML5 Canvas**: All animations rendered on layered canvas elements
- **Vanilla JavaScript**: No frameworks or libraries required
- **CSS3**: Media queries for responsive design, animations for terminal cursor
- **Google Fonts**: VT323 font for retro terminal aesthetic

## 📐 Architecture

### Canvas Layers (z-index order)
1. `#bgCanvas` (z-index: 1) - Rose petals and sparkles background layer
2. `#heartCanvas` (z-index: 50) - Particle heart and text formation
3. `#terminal` (z-index: 100) - Terminal text overlay
4. `#spotlightCanvas` (z-index: 200) - Dark room spotlight effect
5. `#cursorCanvas` (z-index: 9998) - Animated cursor effects

### Key Functions
- `runBootSequence()`: Terminal typing animation
- `triggerReveal()`: Transitions from terminal to heart reveal
- `initParticles()`: Creates heart and text particle system with smart scaling
- `animateCursor()`: Renders animated heartbeat cursor with trail
- `animateBg()`: Rose petal falling and sparkle effects
- `animateSpotlight()`: Interactive flashlight effect

## 🎯 Browser Compatibility

Works on all modern browsers:
- ✅ Chrome/Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

**Note**: Custom cursor animations are disabled on touch devices for optimal mobile experience.

## 📱 Responsive Breakpoints

- **Desktop** (≥768px): Full effects with spotlight and animated cursor
- **Tablet** (≤768px): Smaller text, no custom cursor
- **Mobile** (≤480px): Further reduced sizes, auto-reveal, touch-optimized

## 🎨 Color Palette

**Terminal**:
- Background: `#000000` (Black)
- Text: `#0f0` (Neon Green)
- Error: `#ff0000` (Red)

**Hearts & Petals**:
- Main Heart: `#ff3366`
- Petals: `#ff6b8a`, `#ff8fa3`, `#ffb3c1`, `#f4a0b5`, `#e8556d`, `#fcd5ce`, `#fff0f3`, `#c9184a`
- Cursor Heart: `#ff0055`

## 📄 License

Free to use and customize for personal Valentine's Day surprises! 💝
