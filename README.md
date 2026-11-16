# PIXEL-DSP v1.2 — P455 MDN Sidecar

![gui](path/to/image.png)


Deterministic vector geometry + raster material reconstruction of the **Pulsar Modular P455 MDN Sidecar** (Marc Daniel Nelson signature console summing plugin).

**Illustrator owns geometry. Photoshop owns material. Neither crosses the line.**

- Mode: **B · Hybrid** (default)
- Panel: `920 × 520` px (integer bounds)
- Bridge: flat PNG + `placement.json` only (PSD never ships)
- Rules: R1–R12 (vector) + RP1–RP13 (raster) enforced

## Structure

```
PIXEL-DSP-P455-MDN-Sidecar/
├── README.md
├── docs/
│   └── PIXEL-DSP-v1.2-System-Prompt.md   (companion contract)
├── ir/
│   └── design_ir.json                   (primitives + groups)
├── svg/
│   └── panel.svg                        (vector source of truth)
├── jsx/
│   ├── illustrator_panel.jsx
│   └── photoshop_composite.jsx
├── psd_plan/
│   └── layer_tree.json                  (PSD groups + comps)
├── manifest/
│   ├── placement.json
│   ├── filmstrip.json
│   └── build_manifest.json
└── exports/                             (generated PNGs @1x/@2x)
```

## Controls mapped

| Section          | Components                                      |
|------------------|-------------------------------------------------|
| Top metering     | L/R RMS VU, Global In/Out, Bias, 2CH/8CH        |
| Right top        | Analog / Line Amp toggles                       |
| EQ bank          | 4 bands (blue freq / dark gain), multipliers, shelf/peak, filter LED stack |
| Compressor row   | Threshold, Attack, Release, Output, Ratio A/B, S/C |
| Right side       | Output L / R faders (linked) + badge            |

## Build

```bash
# After emitting IR / SVG / JSX
pixelbot build spec.json --out build/ \
  --svg --jsx --filmstrip --png --psd-plan --composite
```

## License

PIXEL-DSP contract + reconstruction for educational / design-system use.  
Original plugin IP belongs to Pulsar Modular / Marc Daniel Nelson.
