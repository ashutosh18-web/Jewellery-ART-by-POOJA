# POOJA — The Deep End

> Fine jewellery storefront built as one continuous camera move on the scrollbar.

[![Live Demo](https://img.shields.io/badge/🔗_Live_Demo-Visit_Website-2bf0ee?style=for-the-badge&logoColor=060809&labelColor=060809)](https://ashutosh18-web.github.io/Jewellery-ART-by-POOJA/)

🔗 **Live Website Demo**: [https://ashutosh18-web.github.io/Jewellery-ART-by-POOJA/](https://ashutosh18-web.github.io/Jewellery-ART-by-POOJA/)

"POOJA — The Deep End" is an immersive digital storefront for a fine-jewellery house. It opens at night on a woman in black seated at the edge of a lit pool, Paraíba-blue stones at her ears, throat, and hand. 

As the visitor scrolls, the camera cranes up to her face, zooms into a macro shot of the earring, tracks down her neck to the pendant, and glides down to the ring on her hand. Each time the camera settles on a piece, an ivory product card slides in while the film narrows dynamically to keep the jewel perfectly framed. The film rewinds fast to the opening wide shot, an ivory sheet rises with the complete collection, and the page concludes on the oversized **POOJA** wordmark and private viewing request form.

---

## ✨ Features

- **Continuous Camera Scroll Move**: Driven by a pre-decoded 481-frame WebP sequence (24 fps) rendered on an HTML5 Canvas, providing silky smooth scrub response without the latency or async seek dropping of `<video>`.
- **Zero-Rerender Scroll Engine**: Powered by a single `requestAnimationFrame` loop advancing **Lenis**. Position calculation and direct DOM transforms bypass React state during active scrolling, guaranteeing a solid 60/120 fps.
- **Monotone Cubic Time Remapping**: Uses Fritsch–Carlson interpolation (`src/lib/timeRemap.ts`) to speed-ramp the camera move—holding gently on hero moments and traveling swiftly between pieces while guaranteeing scroll monotonicity.
- **Adaptive Split-Screen Presentation**: On desktop, the film narrows dynamically around the focal point of the jewel when product cards slide in; on mobile devices, cards gracefully adapt to bottom sheets.
- **Micro-Interactions & Styling**:
  - Chapter Rail on the right edge tracking camera progression.
  - Interactive shopping bag drawer (`BagDrawer`) with toast confirmations and count bump physics.
  - Custom SVG film grain overlay and animated Paraíba light sweeps (`.glint`).
  - Fluid edge-to-edge wordmark fitting (`useFitText`).
- **Complete Accessibility**: Full keyboard navigation, `aria-*` tags, reduced-motion fallbacks, and high-contrast color choices.

---

## 💎 The Collection

| N° | Piece | Description | Specs | Price |
|---|---|---|---|---|
| **01** | **Undertow Drops** | Pear-cut Paraíba drops hung on articulated links | 2 × 2.05 ct Paraíba, 0.42 ct Diamonds, 28 mm drop | $12,400 |
| **02** | **Deep End Pendant** | Pear-cut stone in a four-claw basket on a delicate skin chain | 3.10 ct Paraíba, 18K white gold, 42 + 3 cm chain | $9,600 |
| **03** | **Night Swim Ring** | Micro-pavé halo cocktail ring with knife-edge band | 3.40 ct Paraíba, 28 × 0.01 ct Halo, 1.8 mm band | $16,200 |
| **Set**| **The Complete Set** | All three pieces cut from the same stone parcel in a bespoke case | Full suite (earrings, pendant, ring) | $38,200 |

---

## 🛠 Tech Stack

- **Framework**: [React 19](https://react.dev/) + [Vite 6](https://vitejs.dev/)
- **Language**: [TypeScript](https://www.typescriptlang.org/) (strict mode)
- **Styling**: [Tailwind CSS v4](https://tailwindcss.com/) with native `@theme` configuration
- **Smooth Scroll**: [Lenis](https://lenis.darkroom.engineering/)
- **Typography**: 
  - *Display*: Bodoni Moda
  - *Body*: Albert Sans
  - *Labels / Numbers*: Martian Mono

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18.0.0 or higher recommended)
- `npm` (or `pnpm` / `yarn`)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ashutosh18-web/Jewellery-ART-by-POOJA.git
   cd Jewellery-ART-by-POOJA
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the local development server:
   ```bash
   npm run dev
   ```

4. Open your browser and visit:
   ```
   http://localhost:5173
   ```

---

## 📜 Scripts

| Command | Description |
|---|---|
| `npm run dev` | Starts the Vite development server with Hot Module Replacement (HMR) |
| `npm run build` | Compiles TypeScript and creates optimized production build in `dist/` |
| `npm run preview` | Previews the production build locally |
| `npm run lint` | Runs TypeScript type checking (`tsc --noEmit`) |

---

## 📁 Project Structure

```text
naiade/
├── public/
│   ├── frames/          # 481 landscape (d/) and portrait (m/) WebP frames
│   └── media/           # Product still photography
├── src/
│   ├── components/      # UI components (Stage, ProductCard, BagDrawer, Nav, etc.)
│   ├── hooks/           # Custom React hooks (useFitText, useReveals, useReducedMotion)
│   ├── lib/             # Scroll loop, time remapping, frame loader, timeline curves
│   ├── content.ts       # Centralized brand copy, specifications, and prices
│   ├── index.css        # Tailwind v4 theme, custom keyframes, display typography
│   ├── App.tsx          # Main application shell
│   └── main.tsx         # Application entry point
├── index.html           # HTML template & font preloads
├── package.json         # Pinned project dependencies
├── tsconfig.json        # TypeScript configuration
└── vite.config.ts       # Vite & Tailwind plugin configuration
```

---

## 📄 License

This project is a concept storefront design and engineering study. Imagery, concepts, and specifications are fictional.
