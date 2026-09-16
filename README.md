# SSVidPlayer (RTX Super Sampling Video Player)

A lightweight, zero-dependency HTML5 video player designed to force native browser AI upscaling (like NVIDIA RTX Video Super Resolution) on your local video files. 

Standalone desktop media players like VLC often lack native support for modern GPU-accelerated video super sampling, or require complex plugins to get working. Web browsers, however, usually support AI upscaling natively. SSVidPlayer wraps your local media in a highly customizable HTML environment, allowing you to scale and crop videos while taking advantage of the AI upscaling your GPU loves to do, all while remaining entirely local and privacy-respecting. 

## Why This Exists

Trying to play upscaled local videos on Windows the way streaming videos upscale is a nightmare. Getting your $1000 GPU to apply native AI upscaling (like NVIDIA RTX VSR) to a local file should be a basic feature, not a complex puzzle requiring bloated media players or obscure plugins that don't even end up working half the time.

SSVidPlayer exists for one core purpose: **to make local video AI upscaling effortless.**

By running local files through a custom HTML5 wrapper, SSVidPlayer utilizes the browser's native hardware upscaling and applies it to your local media just like it would a web stream. 

All the other bells and whistles are just cherries on top of that core purpose.

## Other Features

* **Arbitrary Video Scaling:** Because upscaled low-res videos look tiny natively, the size slider lets you blow the video up to 5x so you can actually enjoy the hardware upscaling on a large monitor.
* **Pixel-Perfect Cropping:** AI upscalers waste resources trying to process encoded black letterbox bars. SSVidPlayer lets you crop the edges in real-time so your GPU only focuses on the actual video content.
* **300% Audio Amplification:** Bypasses standard browser volume limits using the Web Audio API `GainNode`, allowing you to boost quiet audio tracks up to 3x (300%) their native volume.
* **Smart Window Fitting:** A dedicated "Fit to Page" toggle that automatically calculates your viewport and scales the video to utilize the maximum available screen real estate without clipping.
* **Advanced Subtitle Engine:**
  * Drag-and-drop `.srt` support with on-the-fly `.vtt` conversion.
  * Real-time Sub-Sync offset (click the +/- to flip the offset direction and fix out-of-sync text by the millisecond).
  * Draggable subtitles (click and move text anywhere on the screen).
  * Adjustable subtitle font size.
* **Immersive Ambient Glow:** A performance-friendly, GPU-accelerated "ambilight" effect that maps the exact 1-pixel edges of your cropped video onto the background using CSS masks and blur filters.
* **Broad Media Support:** Plays `.mp4`, `.mkv`, and `.webm` video files, but also doubles as an audio player for `.mp3`, `.wav`, `.ogg`, and `.flac` files. 
* **Power User Controls:**
  * Scroll-wheel support for volume, size, and cropping values.
  * Aspect-ratio unlinking (crop top/bottom or left/right independently).
  * Loop toggling for background media.
  * Smart mute memory (remembers your exact volume percentage when unmuting).
  * Auto-hiding, distraction-free UI.
* **100% Local & Private:** Runs entirely in your browser via `URL.createObjectURL`. No servers, no tracking, no uploads.

## How to Use

No installation, no build steps, and no server required.

1. Download `SSVidPlayer.html` by going to the [Release Page](https://github.com/crustyoldhuman/SSVidPlayer/releases) under the newest version.
2. Open `SSVidPlayer.html` in your browser of choice (Firefox/Chrome/Edge recommended for RTX VSR).
3. Drag and drop any `.mp4`, `.mkv`, or `.webm` file into the browser window.
4. (Optional) Drag and drop an `.srt` file to instantly load subtitles. Adjust timing with Sub-Sync controls.

## Shortcuts & Controls

* **Spacebar:** Play / Pause
* **Single Click on player:** Play / Pause
* **Arrow Left / Right:** Skip backward / forward 5 seconds
* **Scroll Wheel (over inputs):** Adjust volume, zoom, sync offsets, and cropping pixel by pixel.
* **Double Click on player:** Open file browser to load new media.
* **Click & Drag (Subtitles):** Reposition subtitles anywhere on the screen.

## Technical Stack

* Vanilla HTML5, CSS3, and JavaScript.
* Utilizes the native HTML5 `<video>` and `<track>` APIs.
* Canvas API for the ambient lighting effect.
* File API for local blob handling.

---
*Developed by [crustyoldhuman](https://github.com/crustyoldhuman)*
