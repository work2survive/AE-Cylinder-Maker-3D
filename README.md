# Cylinder Maker 3D for After Effects (v1.4)

[![Live Browser Simulator](https://img.shields.io/badge/Live%20Demo-AE%20ScriptUI%20Simulator-2c8cff?style=for-the-badge&logo=javascript)](https://work2survive.github.io/AE_JS_builder/?jsx=cylinder_maker.jsx)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Adobe After Effects](https://img.shields.io/badge/Adobe%20After%20Effects-CS6%20--%20CC%202026%2B-9999FF?style=for-the-badge&logo=adobeaftereffects)](https://www.adobe.com/products/aftereffects.html)

A powerful, parametric Adobe After Effects ScriptUI panel that creates, configures, and dynamically rigs 3D Cylinders, circular sectors, and pie wedges built entirely out of native Shape Layers.

> **Live Browser Simulator**: Test and preview this tool interactively in the [AE JS & ScriptUI Simulator](https://work2survive.github.io/AE_JS_builder/?jsx=cylinder_maker.jsx) directly in your web browser without launching After Effects!

---

## ✨ Features

### 1. Parametric 3D Cylinder & Slice Geometry
- **Radius**: Interactive scrubbable slider and numerical input (1 to 500 px).
- **Extrude Depth / Height**: Slider and numerical field (1 to 1000 px).
- **Wall Segments**: Dynamic resolution slider (3 to 64 segments) computing exact chord widths and tangent angles.
- **Slice Options**:
  - **Enable Slice** checkbox to produce pie wedges, open tubes, and semi-cylinders.
  - **Start Angle & End Angle** controls (0° to 360°).
  - Automatically generates radial end walls (`Slice_Start` and `Slice_End`) driven by reactive expressions ensuring walls stay visible and in sync even when slice angles are animated post-creation.

### 2. Tri-Color Palette & Appearance Controls
- **Tri-Color Palette**: 3 independent live color swatches paired with direct hex inputs:
  - Top / Front Cap Color
  - Walls Color
  - Bottom / Back Cap Color
- **Opacity & Stroke**: Global opacity slider, stroke color swatch + hex field, and stroke width slider (0 to 20 px) with dynamic expression to hide stroke at 0.
- **Inner Sides Checkbox**: "Paint inner sides with edge color" (enabled by default) adds internal backing cap faces (`Cap_Top_Inner`, `Cap_Bottom_Inner`) sharing the walls color to prevent contrasting cap colors from leaking through seams at acute viewing angles.
- **Imitate Wall Segments Checkbox**: "Imitate segments of extruded walls" (enabled by default) generates caps matching the extruded polygonal wall facets vertex-for-vertex, eliminating sub-pixel edge leakage.

### 3. Procedural Rigging & Composition Architecture
- Automatically precomposes all walls and caps into an auto-rigged subcomposition with continuous rasterization (`collapseTransformation = true`).
- Controlled via `Cylinder_Master_Controller` with Master Effect Controls on the parent layer, allowing full keyframing and expression linking in the timeline.

---

## 🚀 Installation & Usage

1. Download [`cylinder_maker.jsx`](cylinder_maker.jsx).
2. Place it in your After Effects Scripts folder:
   - **Windows**: `C:\Program Files\Adobe\Adobe After Effects <Version>\Support Files\Scripts\ScriptUI Panels\`
   - **macOS**: `/Applications/Adobe After Effects <Version>/Scripts/ScriptUI Panels/`
3. Restart After Effects or launch via **File > Scripts > Run Script File...**
4. In After Effects, open **Window > cylinder_maker.jsx**.

---

## 📄 License

MIT License. Copyright (c) 2026 [work2survive](https://github.com/work2survive).
