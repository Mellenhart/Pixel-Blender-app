# ![Pixel Blender icon](PixelBlenderSwift/docs/img/icon.png) Pixel Blender

**Image optimizer for Mac.** Blend your pixels. Keep the quality.

![Version](https://img.shields.io/badge/version-3.1.0-b0306a) ![Platform](https://img.shields.io/badge/macOS-14%2B-lightgrey) ![Architecture](https://img.shields.io/badge/Apple%20silicon%20%2B%20Intel-universal-blue) ![Built with](https://img.shields.io/badge/Swift-SwiftUI-orange)

![The Pixel Blender window with an image loaded](PixelBlenderSwift/docs/img/main.png)

## About

Pixel Blender crops, colour-grades and converts your photos for video, socials or the web, one image or a whole batch. Everything happens on your Mac. **Nothing is uploaded** and no internet connection is needed.

It is a native macOS app written in Swift and SwiftUI. It is a single universal app that runs natively on both Apple silicon and Intel Macs.

## Download and install

1. Download **Pixel Blender.dmg** from the [Releases](../../releases) page.
2. Open the disk image and drag **Pixel Blender** onto the **Applications** folder.
3. Open Pixel Blender from Applications.

**First launch.** Pixel Blender is signed only "ad hoc", so macOS asks before it opens the app the first time. Control-click (right-click) the app, choose **Open**, then **Open** again. If macOS still refuses, go to **System Settings › Privacy & Security** and choose **Open Anyway**.

## Minimum requirements

| | |
|---|---|
| **Operating system** | macOS 14 Sonoma or newer |
| **Processor** | Apple silicon or Intel (universal app) |
| **Other** | Nothing else to install. No internet connection needed. |
| **Display** | Window minimum width is 1180 px |

## Quick start

1. Drop one or more images on the window, or press `⌘O`. Any format macOS can read works (JPEG, PNG, HEIC and more), as well as SVG.
2. Choose a **preset** (for example Video or Square) and drag the image to set the crop.
3. Style it, optionally, with a **Look** or the **Adjustments** dials.
4. Choose a **format** (JPEG, PNG, HEIC, PDF or SVG) and quality.
5. Press **Convert and save** (`⌘S`) and choose where to save.

Your original files are never changed, moved or overwritten.

## Key features

- **Presets.** Standard (free size), Video 1920 × 1080, Socials 1080 × 1920, Square 1400 × 1400, 4:3 800 × 600 and Web Icon 512 × 512.
- **Eight one-click Looks** with a strength slider: Nordic Cinematic, Tokyo Neon Noir, Golden Hour Glow, Velvet Mono, Earthy Organic, Lumina Soft Glow, Cyberpunk Punch and Vintage Kodachrome. Each tile previews your own image.
- **Seven adjustment dials.** Exposure, brightness, contrast, vibrance, hue, clarity and tint, with an eyedropper for the tint colour.
- **Formats.** JPEG, PNG, HEIC, PDF (fit to image or A4) and SVG, with a quality dial (5 to 100 %) where it applies.
- **SVG in and out.** SVG files open sharp at their real size. SVG to SVG without Looks or adjustments keeps the original vector shapes.
- **Batch mode.** Each image keeps its own crop, Look and settings. Use *Apply to all* or `⇧`-click a thumbnail to edit every image at once. Export as one ZIP.
- **Web Icon set.** One ZIP with `favicon.ico`, PNG favicons, `apple-touch-icon.png`, `icon-192.png`, `icon-512.png`, `site.webmanifest` and ready-made `<head>` code.
- **Fast live preview.** A quick draft appears at once and sharpens a moment later. A live estimate of the final file size updates as you work.
- **Crop, zoom and inspect.** Zoom 100 to 300 %, view at real 1:1 size, compare Original / Edited, and inspect the final result at 100 % with your chosen format and quality before saving.
- **Private by design.** All processing is local, using Apple's ImageIO and Core Graphics. Finished files are always rendered from the full-resolution original.

### Keyboard shortcuts

| Shortcut | Action |
|---|---|
| `⌘O` | Open images |
| `⌘S` | Convert and save |
| `Esc` | Close the Zoom & inspect view |
| `⌘M` `⌘H` `⌘Q` | Minimise, hide, quit |

## Limitations

- **Very large images are scaled down.** The limit is 120 megapixels and 16,384 px on the long side. Pixel Blender tells you when this happens.
- **Minimum window width of 1180 px**, so every control stays in place.
- **No WebP.** macOS cannot write WebP files. Use HEIC or JPEG instead.
- **Photos are not traced into vectors.** A photo exported as SVG contains the picture as an embedded PNG (about a third larger than the PNG), not as shapes.
- **Looks or adjustments on an SVG turn its shapes into an image.** The panel tells you when this happens.
- **Fixed sizes in most presets.** Only Standard allows free width and height.
- **Panel order is not remembered** between launches.
- **Ad hoc signing.** The app is not notarised, so the first launch needs the steps above.

## Troubleshooting

| Problem | Try this |
|---|---|
| macOS says Pixel Blender "cannot be opened". | Control-click the app and choose **Open**, or use **Open Anyway** in System Settings › Privacy & Security. |
| Width and height fields are greyed out. | Video, Socials, Square, 4:3 and Web Icon have fixed sizes. Choose **Standard** for free sizing. |
| The quality dial is missing. | PNG and SVG are lossless and PDF has no quality setting. Choose JPEG or HEIC. |
| My SVG export cannot be edited as shapes in Illustrator or Figma. | Either the source was a photo, or you applied a Look or adjustment to an SVG. Remove the Look or adjustment to keep the shapes. |
| I cannot find WebP. | macOS cannot write WebP. Use HEIC or JPEG. |
| The exported image is smaller than the original. | The preset sets the output size. Choose **Standard** to keep the original size. |
| An image would not open. | The file may be damaged or in a format macOS cannot read. Try another file. |
| I pressed Convert and nothing was saved. | Enter a file name first (the field pulses when empty), then confirm the Save dialog. Nothing is written until you confirm. |

## Build from source

Requires Xcode command line tools and Swift 5.9 or newer.

```bash
cd PixelBlenderSwift
./build-app.sh
```

The script builds a universal (arm64 + x86_64) release and writes `Pixel Blender.app` to `PixelBlenderSwift/dist`.

## Documentation

The full user guide is available as a PDF: [Pixel-Blender-Documentation.pdf](PixelBlenderSwift/docs/Pixel-Blender-Documentation.pdf).

## Credits and contact

Created by **Ellenhart**. Written in Swift and SwiftUI.

Contact: <https://ellenhart.dk/kontakt>

### Version history

| Version | Main changes |
|---|---|
| 3.1.0 | SVG as import and export format (shapes kept for SVG to SVG). Shift-click to edit all images in a batch at once. Original size (1:1) button. |
| 3.0.0 | First native Mac version in Swift and SwiftUI: Looks, adjustment dials, presets including 4:3 and Web Icon, HEIC and PDF output, batch export, instant preview. |
| 2.0.0 | Electron version of the original web app. Replaced by the native version. |
