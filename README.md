# TR-909 Kick Drum and Stripboard Demos

A small GitHub Pages site for exploring kick-drum sounds inspired by the Roland TR-909. It brings together browser-based sound demos, interactive stripboard diagrams, and component lists.

> **Please note:** The sounds are generated in the browser. They are approximations for listening and learning, not recordings of a TR-909 or simulations of real electronic circuits. The diagrams are references, not verified build instructions.

## Explore the pages

- **[`index.html`](index.html)** — Start here to choose a project page.
- **[`kick-stripboards.html`](kick-stripboards.html)** — Explore four kick designs: the Nein Oh Nein kick, a TR-909-inspired kick, a custom dual-ring kick, and a TR-909-inspired kick with modification controls.
- **[`Kick-drum_stripboards_stepsequencer.html`](Kick-drum_stripboards_stepsequencer.html)** — Try the same kick designs with a 16-step rhythm sequencer. Choose steps, set the tempo, and play the pattern using the selected kick.
- **[`Nein Oh Nein Kick V1.0 (3).html`](Nein%20Oh%20Nein%20Kick%20V1.0%20(3).html)** — Compare a hand-drawn stripboard scan with an annotated component layout, and explore a TR-909 schematic and block diagram.

## What you can do

- Press **TRIG** or the space bar to hear a kick.
- Adjust controls such as pitch, attack, decay, level, accent, noise, and drive. Available controls vary by design.
- Click a component or use the component list to highlight parts on a board. Some pages also let you filter components or compare the drawing with a scan.
- On the custom dual-ring design, inspect the displayed connections and netlist. This design is marked as unbuilt.
- On the modded-kick page, try controls for pitch, tune depth, drive, longer tune or decay, and decay hold. These controls change the audio model; the board does not show added modification circuitry. Exact component values for the referenced modifications have not been verified.

## Run locally

There is no build step or package installation. With Python 3 installed, run this from the repository directory:

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000/> in a browser. Use a modern browser with Web Audio API support to hear the generated sounds; the browser may ask for a click before audio can start.

## Publish with GitHub Pages

The repository is set up as a static site for GitHub Pages. Enable Pages in the repository settings and select the appropriate publishing source for the site. The workflow at `.github/workflows/jekyll-docker.yml` runs a Jekyll build check for pushes and pull requests to `main`.

## Project status

This repository is a collection of standalone HTML pages. The standard and modified TR-909 sounds are software models, and the custom dual-ring design is a documented concept rather than a tested hardware build. Check schematics and component values independently before using them to build a circuit.
