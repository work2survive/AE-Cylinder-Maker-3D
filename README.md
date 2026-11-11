# AE Cylinder Maker 3D (v1.4)

[![Live Browser Simulator](https://img.shields.io/badge/Live%20Demo-AE%20ScriptUI%20Simulator-2c8cff?style=for-the-badge&logo=javascript)](https://work2survive.github.io/AE_JS_builder/?jsx=cylinder_maker.jsx)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Adobe After Effects](https://img.shields.io/badge/Adobe%20After%20Effects-CS6%20--%20CC%202026%2B-9999FF?style=for-the-badge&logo=adobeaftereffects)](https://www.adobe.com/products/aftereffects.html)
[![Built with Antigravity](https://img.shields.io/badge/Built%20With-Antigravity-4285F4?style=for-the-badge&logo=google)](https://deepmind.google/)

**Live Demo**: [https://work2survive.github.io/AE_JS_builder/?jsx=cylinder_maker.jsx](https://work2survive.github.io/AE_JS_builder/?jsx=cylinder_maker.jsx)

A powerful, parametric Adobe After Effects ScriptUI panel that creates, configures, and dynamically rigs 3D Cylinders, circular sectors, and pie wedges built entirely out of native After Effects Shape Layers.

> **Live Browser Simulator**: Test and preview this tool interactively in the [AE JS & ScriptUI Simulator](https://work2survive.github.io/AE_JS_builder/?jsx=cylinder_maker.jsx) directly in your web browser without launching After Effects!

---

## ✨ Features

### 1. Parametric 3D Cylinder & Slice Geometry
- **Radius**: Interactive scrubbable slider and numerical input ($1\text{ to }500\text{ px}$).
- **Extrude Depth / Height**: Slider and numerical field ($1\text{ to }1000\text{ px}$) along the extrusion axis.
- **Wall Segments**: Dynamic resolution slider ($3\text{ to }64\text{ segments}$) computing exact chord widths and tangent angles ($2 R \sin(\pi/N)$).
- **Slice Options**:
  - **Enable Slice** checkbox to generate radial pie wedges, open tubes, and semi-cylinders.
  - **Start Angle & End Angle** controls ($0^\circ\text{ to }360^\circ$).
  - Automatically generates radial end walls (`Slice_Start` and `Slice_End`) driven by reactive expressions ensuring walls stay visible and in sync even when slice angles are animated post-creation.

### 2. Tri-Color Palette & Seam Protection
- **Tri-Color Palette**: 3 independent live color swatches paired with direct hex inputs (`#RRGGBB`):
  - **Top / Front Cap Color**
  - **Walls Color**
  - **Bottom / Back Cap Color**
- **Opacity & Stroke**: Global opacity slider, stroke color swatch + hex field, and stroke width slider ($0\text{ to }20\text{ px}$) with dynamic expression to hide stroke at 0.
- **Inner Sides Checkbox**: "Paint inner sides with edge color" (enabled by default) adds internal backing cap faces (`Cap_Top_Inner`, `Cap_Bottom_Inner`) sharing the walls color to prevent contrasting cap colors from leaking through seams at acute viewing angles.
- **Imitate Wall Segments Checkbox**: "Imitate segments of extruded walls" (enabled by default) generates caps matching the extruded polygonal wall facets vertex-for-vertex, eliminating sub-pixel edge leakage.

### 3. Procedural Rigging & Composition Architecture
- Automatically precomposes all walls, caps, and slice walls into an auto-rigged subcomp with continuous rasterization (`collapseTransformation = true`).
- Controlled via `Cylinder_Master_Controller` with Master Effect Controls on the parent layer, allowing full keyframing and expression linking in the timeline.

---

## 🎛️ Exposed Controls Reference

Once created, the master layer contains the following controls:

| Control Name | Type | Description |
|---|---|---|
| **Radius** | Slider Control | Base cylinder radius in pixels ($1\text{--}500\text{ px}$). |
| **Extrude Height** | Slider Control | Extrusion length in pixels ($1\text{--}1000\text{ px}$). |
| **Wall Segments** | Slider Control | Polygonal resolution ($3\text{--}64\text{ segments}$). |
| **Enable Slice** | Checkbox Control | Toggles slice sector mode on / off. |
| **Start Angle** | Slider Control | Slice opening start angle ($0^\circ\text{--}360^\circ$). |
| **End Angle** | Slider Control | Slice opening end angle ($0^\circ\text{--}360^\circ$). |
| **Top Cap Color** | Color Control | Fill color for the front / top circular cap. |
| **Walls Color** | Color Control | Fill color for the extruded perimeter wall facets. |
| **Bottom Cap Color** | Color Control | Fill color for the back / bottom circular cap. |
| **Global Opacity** | Slider Control | Opacity percentage for the entire cylinder ($0\text{--}100\%$). |
| **Stroke Color** | Color Control | Color for wall and cap outline strokes. |
| **Stroke Width** | Slider Control | Stroke thickness in pixels ($0\text{--}20\text{ px}$). |

---

## 🚀 Installation & Usage

### Option 1: Dockable Panel (Recommended)
1. Download [`cylinder_maker.jsx`](cylinder_maker.jsx).
2. Place it in your After Effects `ScriptUI Panels` directory:
   - **Windows**:
     ```text
     C:\Program Files\Adobe\Adobe After Effects <Version>\Support Files\Scripts\ScriptUI Panels\
     ```
   - **macOS**:
     ```text
     /Applications/Adobe After Effects <Version>/Scripts/ScriptUI Panels/
     ```
3. Restart After Effects.
4. Open from the menu: **Window > cylinder_maker.jsx**.

### Option 2: Run Without Installing
1. In After Effects, navigate to **File > Scripts > Run Script File...**
2. Browse to and select `cylinder_maker.jsx`.

---

## 💡 Use Cases

- **3D Infographics & Pie Charts**: Build 3D pie charts, donut charts, and cylinder progress gauges.
- **Packaging & Product Visualization**: Render cans, bottles, coins, pucks, dials, and wheels.
- **Architectural & Sci-Fi Motion Graphics**: Create curved tunnels, radar sweeps, and mechanical shafts.

---

---

## 🤖 Acknowledgments

Engineered, architected, and co-developed using **[Google DeepMind Antigravity](https://deepmind.google/)** agentic coding assistant.

## 📄 License

MIT License. Copyright (c) 2026 [work2survive](https://github.com/work2survive).