# Image Sensor Explorer (v3.6)

One CMOS image sensor, followed from photons to bits: image quality, dynamic range, timing and parallelism.

# Image Sensor Explorer

A concept-phase design tool for CMOS image sensors. It connects the product
spec (dynamic range, read noise, frame rate per mode, MIPI link) to the
architecture (pixel, column ADC, timing, datapath, block budgets, hygiene)
in one live model, so we can see what each choice costs in both directions.

**Live tool:** https://c6d59zm4k6-stack.github.io/ImageSensorExplorer/

## Quick start
1. Pick a sensor in the top-right dropdown: a scenario or a reference sensor.
2. Start on **Overview**: three checks (image quality, dynamic range, timing),
   the mode table, and "What it would take" when a target is missed.
3. Change inputs in the left panel and press **Update results**.
4. Press **📌 Pin as baseline** before a change to compare before and after.

## Tabs
- **Overview** – targets, modes, checks, calibration against public data
- **① Image quality** – noise budget, SNR curves, simulated images
  (low light, fixed pattern, HDR range, banding)
- **Architecture** – the chip as blocks, supplies and clocks
- **② Dynamic range** – where range is kept or lost from photons to bits
- **③ Timing** – line and frame length per mode, which limit binds
- **Block detail** – analog noise and speed budgets, hygiene specs
- **Equations** – how every number was derived

## Sensors included
- Scenarios (hypothetical): Mobile 50 MP, Automotive 8 MP HDR,
  Industrial 5 MP global shutter
- References: Sony IMX290, IMX183, IMX296; onsemi MT9P031; OmniVision OV9281

All references are derived from data available publicly. It may or may not be correct.

## Limitations
Simplified, physically grounded models for early architecture work, not a
circuit or optical simulator. Not modeled yet: power and area, split-pixel
HDR, per-mode blanking, shortened reset ramps.

## About
Single-file React app, bundled into `index.html` (no install, no network
needed). Sensor names are trademarks of their owners; this project is not
affiliated with any of these companies and is a personal project.
