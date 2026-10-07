# Open Me

A small interactive web page for asking someone out, built as a passed notebook note.

It opens as a folded note. Tap it to unfold the question with two boxes: **Yes** and **No**. The No box won't let itself get clicked. It runs away from the cursor (or a finger on mobile), the Yes box grows with every miss, and a red-pen comment teases each attempt. Choosing Yes sets off confetti.

## How it works

- **Vanilla HTML, CSS, and JavaScript** in a single `index.html`, with no build step and no dependencies
- **Evasive button:** pointer-proximity detection with `mousemove` and `Math.hypot`, plus `touchstart`, `pointerdown`, `click`, and keyboard handlers, so it can't be clicked on desktop, mobile, or by keyboard
- **Fair repositioning:** each jump lands inside the viewport with a 16px gutter, at least 140px from where it was, and stays clamped on resize
- **Confetti** drawn on a `<canvas>` with `requestAnimationFrame`, skipped when `prefers-reduced-motion` is set
- **Spoiler-safe link preview:** the first screen is a sealed note, and the Open Graph tags only say "Open Me", so the message stays hidden in text-message previews
- **Live notifications** through [ntfy](https://ntfy.sh): pings sent with `navigator.sendBeacon` when the note is opened, answered, or abandoned (add `#test` to the URL to mute them)
- **Notebook paper** built entirely from CSS gradients (ruled lines, margin line, fold crease) with Google Fonts handwriting faces

## Run it

Open `index.html` in any browser, or visit the GitHub Pages site.
