# RAiDOS v2.0 // #RAICANDISH

> A living open-world text adventure.  
> AI runs 100% in the visitor's browser — no API key, no server, no account.  
> Powered by WebLLM + Broswer Ai 

---

## How it works

1. Visitor lands on the page
2. RAi boot sequence plays
3. WebLLM downloads Phi-3.5 Mini (~2.4 GB) into the browser's cache
4. Model is cached permanently — instant on every return visit
5. The entire AI runs locally in the browser. No data leaves the device.

**Zero setup for visitors. Zero cost to host.**

---

## Deploy

Push to GitHub → Settings → Pages → main branch / root → done.

The service worker (`sw.js`) automatically injects the `Cross-Origin-Isolation` headers
that WebLLM needs for `SharedArrayBuffer` (multi-threaded WASM inference).  
This works on GitHub Pages with no extra configuration.

---

## Files

```
raidOS/
├── index.html   — entire app, self-contained
├── sw.js        — service worker (COOP/COEP headers + cache)
├── _headers     — Netlify/Cloudflare Pages header rules
└── README.md
```

No build step. No npm. No framework. One HTML file.

---

## Available models (switchable in Options)

| Model | Size | Notes |
|---|---|---|
| Phi-3.5 Mini (default) | ~2.4 GB | Best quality narrative |
| Phi-3 Mini Q4 | ~1.8 GB | Good balance |
| Llama 3.2 1B | ~600 MB | Fastest first load |
| SmolLM2 1.7B | ~1.0 GB | Lightweight |

All models are fetched from the MLC CDN and cached in the browser.
Switch models via ESC → Options → AI Model, or `/model [id]` in the terminal.

If Phi-3.5 Mini fails to load (low RAM/VRAM), RAiDOS automatically falls back
to Llama 3.2 1B.

---

## Commands

| Command | Action |
|---|---|
| `/help` | show all commands |
| `/look` | re-describe current location |
| `/go [place]` | travel somewhere |
| `/inv` | show inventory |
| `/lore` | world lore discovered |
| `/visited` | locations visited |
| `/options` | open options (also: ESC) |
| `/model [id]` | switch AI model |
| `/clear` | clear terminal |
| `/new` | start a new world |

Or just type freely — speak, act, build the world.

---

## Options (ESC)

- Font size, terminal width
- Scanline CRT effect
- Sound master / volume / ambient drone / keyclick
- AI model selector
- World tone: Post-Apocalyptic / Cyberpunk / Dark Fantasy / Sci-Fi / Noir / Void
- New world (resets session)

---

## Browser requirements

WebLLM requires a modern browser:
- Chrome 113+ or Edge 113+ (best — full WebGPU)
- Firefox (CPU fallback — slower but works)
- Safari 17.4+ (partial support)

Minimum ~4 GB RAM recommended for Phi-3.5 Mini.  
For low-RAM devices, switch to Llama 3.2 1B (~600 MB) in Options.

---

## Built by

**Rai Candish**  
`#RAICANDISH` `#RYCANDISH` `#RYANCANDISH`  
`#RAiBios` `#RAiOS` `#RAiDOS` `#RAiBOOT` `#RAi` `#MKALTRAi`  
`#RAiHISTORY` `#MKRAINAME` `#METAþORR` `#MKCTRLALTDEl`
