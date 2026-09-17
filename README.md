<p align="center"><img width="750" alt="Iconbanner" src="https://github.com/user-attachments/assets/577609d7-7437-4fb1-9a49-f26d85aa19b6" /></p>
<br>

# SSVidPlayer (RTX Super Sampling Video Player)

A lightweight, zero-dependency HTML5 video player designed to apply native browser AI video upscaling (like NVIDIA RTX Video Super Resolution) to your local `.mp4` files, all while remaining entirely local and privacy-respecting.
<br><br>
<p align="center"><img width="900" alt="DefaultPageScreenie" src="https://github.com/user-attachments/assets/6696d7c6-3e21-4b2c-abbe-9e9000d28149" /></p>

## Why This Exists

Trying to play upscaled local videos on Windows the way streaming videos upscale is a sh**show nightmare. Getting your $1000+ GPU to apply native AI upscaling (like NVIDIA RTX VSR) to a local file should be a basic feature, not a complex puzzle requiring bloated media players or obscure plugins that don't even end up working half the time.

SSVidPlayer exists for one core purpose: **to make local video AI upscaling easy.**

By running local files through a custom HTML5 wrapper, SSVidPlayer utilizes the browser's native hardware upscaling and applies it to your local media just like it would a web stream. If your upscaling works on YouTube or other streaming videos, it will work on SSVidPlayer as well.

All the other bells and whistles are just cherries on top of that core purpose.
<br><br>

<p align="center"><img width="900" alt="VidPlayingScreenie" src="https://github.com/user-attachments/assets/7c018495-d111-4a03-8994-733c2f91ec5d" /></p>

## Other Features

* **Video Scaling:** Because upscaled low-res videos look tiny natively, the size slider lets you blow the video up to 5x so you can actually enjoy the hardware upscaling on a large monitor without needing to go full screen.
* **Edge Cropping:** Burned in black edges ruin the ambient glow effect, and AI upscalers waste resources trying to process encoded black letterbox bars. SSVidPlayer lets you crop the edges in real-time to fix both of these problems.
* **300% Audio Amplification:** Bypasses standard browser volume limits using the Web Audio API `GainNode`, allowing you to boost quiet audio tracks up to 3x (300%) their native volume. (works in Firefox, not supported in Chromium)
* **Smart Window Fitting:** A dedicated **Fit to Page** toggle that automatically calculates your viewport and scales the video to utilize the maximum available screen real estate without clipping.
* **Advanced Subtitle Engine:**
  * Drag-and-drop `.srt` support with on-the-fly `.vtt` conversion.
  * Real-time **Sub-Sync** offset (click or scroll the **+** / **-** to flip the offset direction and fix out-of-sync text by the millisecond).
  * Draggable subtitles (click and move text anywhere on the screen)
  * Adjustable subtitle font size.
  * Aspect-ratio unlinking (crop top/bottom or left/right independently)
* **Immersive Ambient Glow:** A performance-friendly, GPU-accelerated "ambilight" effect that maps the exact 1-pixel edges of your cropped video onto the background using CSS masks and blur filters. Includes intensity slider (not pictured in above screenshot).
* **Broad Media Support:** Plays `.mp4`, `.mkv`, and `.webm` video files, but also doubles as an audio player for `.mp3`, `.wav`, `.ogg`, and `.flac` files. 
* **Power User Controls:**
  * Scroll-wheel support for volume, size, and cropping values.
  * Loop toggling for background media.
  * Smart mute memory (remembers your exact volume percentage when unmuting).
  * Auto-hiding, distraction-free UI.
* **100% Local & Private:** Runs entirely in your browser via `URL.createObjectURL`. No servers, no tracking, no uploads.

## How to Use

1. Download `SSVidPlayer.html` by going to the [Release Page](https://github.com/crustyoldhuman/SSVidPlayer/releases) under the newest version.
2. Open `SSVidPlayer.html` in your browser of choice (Firefox/Chrome/Edge recommended for RTX VSR).
3. Drag and drop any `.mp4`, `.mkv`, or `.webm` file into the browser window.
4. (Optional) Drag and drop an `.srt` file to instantly load subtitles. Adjust timing with **Sub-Sync** controls.
5. You can drag and drop the video file and `.srt` file at the same time or separately. 
6. `.mp4` FILES ARE HEAVILY SUGGESTED. You may get mixed results with other filetypes depending how they were encoded, but all `.mp4`s should work. 

## Shortcuts & Controls

* **Spacebar:** **Play** / **Pause**
* **Single Click on player:** **Play** / **Pause**
* **Arrow Left** / **Right:** Skip backward / forward 5 seconds
* **Scroll Wheel (over inputs):** Adjust volume, zoom, sync offsets, and cropping pixel by pixel.
* **Double Click on player:** Open file browser to load new media.
* **Click & Drag (Subtitles):** Reposition subtitles anywhere on the screen.

## Known Limitations

* `srt`files are required for subtitles. Embedded subtitles will not work due to browser limitations. The page is simply blind to embedded subtitles and there is nothing I can do about it.
* The ambilight glow effect will look wonky if there are any black edges or bars permanently embedded into a playing video file. Use the cropping tool to fix this problem.
* Currently there is no playlist support, but I could add it if it seems like people would use it. I personally don't need a playlist feature. Drop a message if you'd like a playlist.
* The 300% boosted volume feature does not work on Edge/Chromium browsers due to how they pipe out their audio and the limitations of zero-dependency HTML5 page. If you want boosted volume, you'll have to switch to Firefox (oh no! /s). 

## Technical Stack

* Vanilla HTML5, CSS3, and JavaScript.
* Utilizes the native HTML5 `<video>` and `<track>` APIs.
* Canvas API for the ambient lighting effect.
* File API for local blob handling.

---
*Created with love by [crustyoldhuman](https://github.com/crustyoldhuman)*
