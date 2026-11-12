# Foundation IP Catalog Explorer

Interactive website/app to scroll through foundation IP building blocks, view RTL/Verilog models, I/O ports, conceptual layout notes, and create derivatives.

**Educational models only** — not foundry-qualified. Targeting conceptual use on TSMC 12nm, Samsung 14nm, GlobalFoundries 12nm.

## How to use
1. Open `index.html` in a browser (or enable GitHub Pages from the main branch).
2. Click blocks in the sidebar to explore RTL, ports, and layout notes.
3. Use the "Create Derivative" tab to generate a starting Verilog skeleton for a modified block.

## Structure
- `index.html` — Single-file web app
- `rtl/` — Verilog models
- `docs/` — Cookbook overview

Generated with specialized Grok bots for catalog, design, architecture, specs, and testing.
