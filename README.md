# SELENE — Watch the Earth rise

A cinematic, scroll-driven web experience for a fictional lunar expedition company. The journey opens behind a veil of cosmic dust that clears onto the grey cratered surface of the Moon, where the Earth climbs out from behind the horizon under an engineered `EARTHRISE` title while a lone astronaut stands silhouetted on a rock in the foreground.

---

## ✨ Features & Architecture

- **Single rAF Scroll Loop**: Driven by a single `requestAnimationFrame` loop in `src/lib/scroll.ts` that advances [Lenis](https://github.com/darkroomengineering/lenis) and writes styles directly to the DOM. Zero React state updates occur during scroll, preventing mid-scroll re-renders.
- **6-Layer Parallax Earthrise**: Stacked and pinned photographic layers (`sky`, `earth`, `moonscape`, `frame`, `astronaut`, `ground`), each moving at distinct rates with dedicated desktop (`d/`) and mobile (`m/`) cuts.
- **Cosmic Dust Clearing**: Interactive canvas particle veil that disperses upward as scrolling begins, clearing completely before the Earth starts rising.
- **Live Telemetry HUD**: Real-time mission elapsed time clock (`T+ HH:MM:SS`), Earth elevation readout (`0.0°` → `12.4°`), and landing coordinates (`Mare Tranquillitatis · 0.67°N 23.47°E`).
- **Mission Log Reel**: Horizontal card slider synchronized with vertical scroll progress, smoothly scaling and focusing the card closest to center.
- **Scroll-Inked Trajectory**: A 384,400 km Earth → Moon flight path drawn across four distinct orbital legs (`Parking orbit`, `Trans-lunar injection`, `Lunar orbit insertion`, `Descent`), complete with a moving capsule and distance readout.
- **Mission Classes**: Tiered expedition tiers (`Orbiter`, `Lander`, `Resident`) featuring dynamic SVG orbit rings representing mission duration.
- **Launch Window Countdown & Manifest Form**: Ticking countdown to the next conceptual launch window (Apollo 11 anniversary) with client-side manifest drafting.
- **Precision Typography**: Google Fonts integration using **Michroma** for engineered display headers, **Manrope** for body text, and **IBM Plex Mono** for telemetry.

---

## 🛠️ Tech Stack

- **Framework**: [React 19](https://react.dev/) + [TypeScript](https://www.typescriptlang.org/)
- **Bundler**: [Vite 6](https://vitejs.dev/)
- **Styling**: [Tailwind CSS v4](https://tailwindcss.com/) with `@tailwindcss/vite`
- **Smooth Scroll**: [Lenis](https://lenis.darkroom.engineering/)

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- `npm`

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/deepak7-shadow/Earth-scrolls-animation-.git
   cd Earth-scrolls-animation-
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the local development server:
   ```bash
   npm run dev
   ```
   Open [http://localhost:3006](http://localhost:3006) in your browser.

---

## 📜 Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Runs the Vite dev server at `http://localhost:3006` |
| `npm run build` | Compiles and builds the production bundle in `dist/` |
| `npm run preview` | Previews the production build locally at port 3006 |
| `npm run lint` | Runs TypeScript type checking (`tsc --noEmit`) |

---

## 📂 Project Structure

```
├── public/
│   ├── layers/          # Desktop (d/) and Mobile (m/) parallax layer assets
│   └── media/           # Mission log stills and OG images
├── src/
│   ├── components/
│   │   ├── Chrome.tsx       # Header, navigation, and footer
│   │   ├── Earthrise.tsx    # 6-layer hero section with cosmic dust & telemetry
│   │   ├── MissionLog.tsx   # Horizontal scroll-driven mission reel
│   │   ├── Missions.tsx     # Expedition tier cards with orbit rings
│   │   ├── Reserve.tsx      # Countdown timer & waitlist manifest form
│   │   └── Trajectory.tsx   # 4-leg flight path drawing & distance counter
│   ├── hooks/
│   │   ├── useFitText.ts
│   │   ├── useReducedMotion.ts
│   │   └── useReveals.ts
│   ├── lib/
│   │   ├── math.ts          # Interpolation, clamping, and scroll math
│   │   └── scroll.ts        # Global rAF loop and Lenis coordinator
│   ├── App.tsx
│   ├── content.ts       # Copy and data structures
│   ├── index.css        # Tailwind v4 theme & token definitions
│   └── main.tsx
├── index.html
├── package.json
├── tsconfig.json
└── vite.config.ts
```

---

## 📄 License

MIT
