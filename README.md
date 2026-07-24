# 🌸 Pétale — Premium Flower Boutique Landing Page

[![Astro](https://img.shields.io/badge/Astro-v5-ff5d01?style=for-the-badge&logo=astro&logoColor=white)](https://astro.build/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Vite](https://img.shields.io/badge/Vite-v6-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-Deployed-22c55e?style=for-the-badge&logo=github)](https://ojitxslml.github.io/FlowerShopLandingPage)

An elegant, responsive, and performance-optimized landing page for **Pétale**, a luxury boutique florist based in Santiago, Chile. Built with **Astro** and **Tailwind CSS v4**, this project delivers zero-JS static HTML by default, smooth micro-interactions, rich typography, and modern visual aesthetics.

---

## 📸 Overview & Features

- 🌹 **Curated Arrangement Catalog**: Interactive floral collection showcase with category filtering (Roses, Tulips, Orchids, Peonies).
- 🚚 **Boutique Services**: Highlights same-day delivery, subscription plans, event styling, and corporate arrangements.
- 📍 **Store Locations**: Interactive store finder detailing physical locations, operating hours, and contact details across Santiago.
- 💬 **Social Proof & Testimonials**: Customer ratings, verified reviews, and brand story highlighting artisanal floral craft.
- ⚡ **Lightning Fast Performance**: Achieves top-tier Lighthouse scores through Astro's component architecture and static pre-rendering.
- 🎨 **Luxury Aesthetic**: Elegant color palette (cream, blush rose, deep burgundy, charcoal) paired with classic editorial typography (*Playfair Display* & *Inter*).
- 📱 **Fully Responsive & Accessible**: Mobile-first fluid design with semantic HTML5 standards and smooth scroll animations.

---

## 🏛️ Architecture & System Design

The application is engineered as a Static Site Generated (SSG) web app using **Astro** and styled with **Tailwind CSS v4** (`@tailwindcss/vite`).

```text
 ┌────────────────────────────────────────────────────────────────────────┐
 │                              Layout.astro                              │
 │  (HTML5 Shell, Global SEO Meta, Fonts, Favicon & Scroll Observer)       │
 └───────────────────────────────────┬────────────────────────────────────┘
                                     │
                                     ▼
 ┌────────────────────────────────────────────────────────────────────────┐
 │                             index.astro                                │
 │                        (Main Page Controller)                          │
 └───────────────────────────────────┬────────────────────────────────────┘
                                     │
    ┌──────────────┬─────────────────┼────────────────┬──────────────┐
    ▼              ▼                 ▼                ▼              ▼
┌────────┐   ┌────────────┐   ┌──────────────┐  ┌───────────┐  ┌──────────────┐
│ Navbar │   │    Hero    │   │FlowersGrid & │  │   About   │  │   Services   │
│        │   │            │   │ FlowerCard   │  │           │  │              │
└────────┘   └────────────┘   └──────────────┘  └───────────┘  └──────────────┘
    │              │                 │                │              │
    └──────────────┴─────────────────┼────────────────┴──────────────┘
                                     ▼
                  ┌──────────────────────────────────────┐
                  │ Testimonials, Location, Contact &    │
                  │              Footer                  │
                  └──────────────────────────────────────┘
```

### Architectural Key Points

1. **Static Site Generation (SSG)**: Pages are pre-rendered into optimal HTML/CSS at build time, eliminating unnecessary client-side JavaScript overhead.
2. **Modular Component Architecture**: Reusable Astro components located in `src/components/` isolate UI sections (Navbar, Hero, FlowersGrid, Location, Services, etc.) and component fragments (FlowerCard).
3. **Global Styling & Theme Extensions**: Defined in `src/styles/global.css`, leveraging Tailwind CSS v4 directives along with standard CSS custom properties for custom brand colors and `.reveal` keyframe scroll animations.
4. **Scroll-Driven Animation Engine**: Lightweight inline JavaScript in `Layout.astro` uses the native `IntersectionObserver` API to detect visible sections on scroll and trigger smooth entry transitions (`.reveal.visible`).
5. **CI/CD Pipeline**: GitHub Actions workflow (`.github/workflows/deploy.yml`) automatically builds static assets and publishes them to GitHub Pages upon pushing to the `main` branch.

---

## 📁 Project Structure

```text
FlowerLanding/
├── .github/
│   └── workflows/
│       └── deploy.yml           # Automated deployment to GitHub Pages
├── public/                      # Static assets (images, icons, favicon)
├── src/
│   ├── components/              # Modular UI components
│   │   ├── About.astro          # Brand origins & philosophy
│   │   ├── ContactCTA.astro     # Order inquiry & CTA section
│   │   ├── FeatureBanner.astro  # Key guarantees & badges
│   │   ├── FlowerCard.astro     # Individual product card component
│   │   ├── FlowersGrid.astro    # Product grid & category filters
│   │   ├── Footer.astro         # Footer links & newsletter signup
│   │   ├── Hero.astro           # Main visual banner & primary CTAs
│   │   ├── Location.astro       # Physical store locations & business hours
│   │   ├── Navbar.astro         # Sticky header with mobile menu
│   │   ├── Services.astro       # Floral services & subscription plans
│   │   └── Testimonials.astro   # Customer reviews & ratings
│   ├── layouts/
│   │   └── Layout.astro         # Main page wrapper, head tags & scroll scripts
│   ├── pages/
│   │   └── index.astro          # Main entry page assembling all sections
│   └── styles/
│       └── global.css           # Tailwind v4 import, custom theme & animations
├── astro.config.mjs             # Astro configuration (base path & Vite plugins)
├── package.json                 # Node dependencies & project scripts
└── tsconfig.json                # TypeScript configuration
```

---

## 🛠️ Tech Stack & Dependencies

| Technology | Role | Version |
| :--- | :--- | :--- |
| **[Astro](https://astro.build/)** | Static Web Framework | `^7.1.3` |
| **[Tailwind CSS](https://tailwindcss.com/)** | Utility-First CSS Framework | `^4.3.3` |
| **[Vite](https://vitejs.dev/)** | Build Tool & Plugin Integrations | Integrated via `@tailwindcss/vite` |
| **Node.js** | JavaScript Runtime Engine | `>=22.12.0` |

---

## 🚀 Getting Started

### Prerequisites

Ensure you have [Node.js](https://nodejs.org/) (version `22.12.0` or higher) installed on your system.

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ojitxslml/FlowerShopLandingPage.git
   cd FlowerShopLandingPage
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the local development server:**
   ```bash
   npm run dev
   ```
   Open your browser and navigate to `http://localhost:4321/FlowerShopLandingPage/`.

---

## 📜 Available Scripts

| Command | Action |
| :--- | :--- |
| `npm run dev` | Launches local development server with hot-reload at `http://localhost:4321` |
| `npm run build` | Builds the static site output to `./dist` for production |
| `npm run preview` | Previews the build output locally from `./dist` |
| `npm run astro` | Runs Astro CLI commands (e.g. `npm run astro check`) |

---

## 🚢 Deployment

Deployment is completely automated via **GitHub Actions**.

Whenever changes are merged or pushed to the `main` branch, `.github/workflows/deploy.yml` will automatically:
1. Checkout the repository code.
2. Setup Node.js 22 environment.
3. Install dependencies via `npm ci`.
4. Build static HTML/CSS/JS files via `npm run build` into `./dist`.
5. Deploy static assets to **GitHub Pages**.

The live site is published at: **[https://ojitxslml.github.io/FlowerShopLandingPage/](https://ojitxslml.github.io/FlowerShopLandingPage/)**

---

## 📄 License

This project is licensed under the MIT License — see the project repository for details.
