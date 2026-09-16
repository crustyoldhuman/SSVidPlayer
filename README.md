# SSVidPlayer (RTX Super Sampling Video Player)

A lightweight, zero-dependency HTML5 video player designed to force native browser AI upscaling (like NVIDIA RTX Video Super Resolution) on your local video files. 

Standalone desktop media players like VLC often lack native support for modern GPU-accelerated video super sampling, or require complex plugins to get working. Web browsers, however, usually support AI upscaling natively. SSVidPlayer wraps your local media in a highly customizable HTML environment, allowing you to scale and crop videos while taking advantage of the AI upscaling your GPU loves to do, all while remaining entirely local and privacy-respecting. 

## Why This Exists

Browsers natively support hardware AI upscaling (like NVIDIA RTX Video Super Resolution) for low-resolution video, but standard drag-and-drop local playback in browsers is a pretty sad experience that leaves a lot to be desired. **SSVidPlayer** solves this by offering:

* **Arbitrary Video Scaling:** Low-res videos are meant to be upscaled, but they look tiny when displayed normally. The size slider lets you scale the video up to 5x so you can actually take advantage of the hardware upscaling on a large screen.
* **Pixel-Perfect Cropping:** AI upscalers get confused by encoded black letterbox bars, trying to process the black space instead of just the image is a waste of resources. SSVidPlayer lets you crop out the edges in real-time so your GPU only focuses on upscaling the actual video content.

## Features

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

## 🛠️ How to Use

No installation, no build steps, and no server required.

1. Download `SSVidPlayer.html` or bookmark the page normally after loading it from here (this way, it will automatically update).
2. Open `SSVidPlayer.html` in your browser of choice (Chrome/Edge recommended for RTX VSR).
3. Drag and drop any `.mp4`, `.mkv`, or `.webm` file into the browser window.
4. (Optional) Drag and drop an `.srt` file to instantly load subtitles. Adjust timing with Sub-Sync controls.
5. Use the **Vid Size** slider to scale the video and trigger your browser's native super sampling.

## ⌨️ Shortcuts & Controls

* **Spacebar:** Play / Pause
* **Single Click on player:** Play / Pause
* **Arrow Left / Right:** Skip backward / forward 5 seconds
* **Scroll Wheel (over inputs):** Adjust volume, zoom, sync offsets, and cropping pixel by pixel.
* **Double Click on player:** Open file browser to load new media.
* **Click & Drag (Subtitles):** Reposition subtitles anywhere on the screen.

## ⚙️ Technical Stack

* Vanilla HTML5, CSS3, and JavaScript.
* Utilizes the native HTML5 `<video>` and `<track>` APIs.
* Canvas API for the ambient lighting effect.
* File API for local blob handling.

---
*Developed by [crustyoldhuman](https://github.com/crustyoldhuman)*
