# Harmony Visualizer

A mobile-first web synthesizer with a live spectrogram and real-time harmony cues. Tap notes on either strip — the visualizer shows you what's sounding, and the harmony bar suggests which other notes will sit well with what you've played.

![screenshot placeholder — open index.html to see it](#)

## Features

- **Two instrument strips** — Keys (Piano, Organ, Bell, Marimba) and String (Guitar, Harp, Bass, Sitar)
- **Live visualizer** — Audition-style scrolling spectrogram or stacked FFT bars
- **Harmony engine** with three modes and sub-options:
  - **Intervals** — pure consonance scoring (P5, P4, M3…)
  - **Chord** — Major, Minor, Maj7, Dom7, min7, Sus4
  - **Scale** — Major, Minor, Penta, Blues, Dorian, Lydian
- **Polyphonic** — tap several notes at once; the harmony bar updates live
- **Adjustable decay** from 0.3s to 5s
- **Mobile-first** — 48px touch targets, no pinch-zoom, safe-area padding

## Running it

It's a single static HTML file. Any static server will do:

```bash
python -m http.server 8080
# then open http://localhost:8080/
```

Or just open `index.html` in a browser that allows `file://` WebAudio (most do after a user gesture).

Deploys as-is to GitHub Pages, Netlify, Vercel, Cloudflare Pages, or any static host.

## Tech

No build step. React 18 and Babel Standalone load from unpkg; JSX is compiled in the browser. Audio synthesis and FFT analysis use the WebAudio API. Two separate `AnalyserNode`s feed the spectrogram so Keys and String can be drawn in their own colors.

## Browser support

Requires WebAudio and ResizeObserver — Chrome 64+, Safari 13.1+, Firefox 69+.
