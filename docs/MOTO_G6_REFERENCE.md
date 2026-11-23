# Motorola Moto G6 — researched reference hardware (2026-11-23)

**Device:** standard Moto G6 (2018), NOT Moto G6 Plus or Play. Public historical measurements, not measurements of our physical test device or ZIMT. Always verify actual OS, RAM, display mode and battery health on user's device.

## Specifications
- Snapdragon 450 (14 nm); 8 x ARM Cortex-A53 up to 1.8 GHz; Adreno 506 GPU.
- RAM variants: 3 GB / 4 GB; storage 32 / 64 GB; 5.7-inch IPS 2160 x 1080 screen (2,332,800 pixels); battery 3000 mAh.
- Android 8.0 originally, Android 9.0 listed for updated units. The user's installed OS is **unverified**.
- 60 Hz UI budget: 16.67 ms/frame (target, NOT observed app performance). Do not assume the GPU can handle many translucent fullscreen passes.

## Published historical measurements
| Benchmark | Moto G6 result | Interpretation |
|---|---:|---|
| Geekbench 4 single | 709 | Legacy CPU benchmark; not comparable to GB5/6 |
| Geekbench 4 multi | 3625 | Legacy CPU benchmark |
| 3DMark Sling Shot ES3.0 | 791–800 | Different test publications / runs |
| 3DMark Sling Shot ES3.0 Graphics | 690 | GPU-focused subscore |
| 3DMark Sling Shot Extreme ES3.1 | 424 (UL aggregate), 442 (Notebookcheck test) | Different samples / methodology |
| GFXBench T-Rex onscreen | 20 fps | Heavy 3D scene, NOT UI FPS |
| GFXBench T-Rex 1080p offscreen | 22 fps | Heavy 3D scene |
| GFXBench Manhattan 3.0 onscreen | 8.9 fps | Heavy 3D scene |
| GFXBench Manhattan ES3.1 onscreen | 5.8 fps | Heavy 3D scene |
| GFXBench Car Chase onscreen | 3.3 fps | Very heavy 3D scene |
| PCMark Work 3.0 | 4505 (UL) | Productivity benchmark |
| PCMark Storage 2.0 sequential read/write | 216 / 39 MB/s (UL) | Reported sample, not guaranteed current storage |

Sources (original URLs):
- Qualcomm platform: https://www.qualcomm.com/smartphones/products/4-series/snapdragon-450-mobile-platform
- Notebookcheck Moto G6 review: https://www.notebookcheck.net/Motorola-Moto-G6-Smartphone-Review.303202.0.html
- Notebookcheck Snapdragon 450 dataset: https://www.notebookcheck.com/Qualcomm-Snapdragon-450-SoC-Benchmarks-und-Specs.299440.0.html
- UL benchmark device database: https://benchmarks.ul.com/hardware/phone/Motorola%2BMoto%2BG6%2Breview
- PhoneArena hardware variants: https://www.phonearena.com/phones/motorola-moto-g6_id10788

## Engineering implications (hypotheses to verify)
- Favor cached static layers, cheap transforms, and bounded overdraw; measure blur, large alpha layers and shadow rendering.
- Avoid decoding oversized PNGs on the animation frame; cache within a measured memory budget. 2160x1080 RGBA_8888 single full-screen buffer ≈8.90 MiB / 9.33 MB, before copies/mipmaps; multiple buffers compound.
- Prioritize immediate input and no per-frame allocations. Profile CPU main thread AND GPU; published 3D fps cannot predict Compose/Canvas UI fps.
- Historical review reported relatively stable sustained graphics performance, but aging battery, OS and thermal environment may change real behavior.

## Verification
Record device model, actual Android API, RAM, display refresh rate, thermal/battery state, app SHA, frame timeline and heap from **real** Moto G6. Status: UNVERIFIED for ZIMT.
