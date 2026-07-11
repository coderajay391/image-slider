# Image Slider 

A simple responsive image slider built with **HTML + CSS + Vanilla JavaScript**.

## Preview
<image scr="./assets/image-slider.png"></image>

## Demo
[watch demo](assets/image-slider.mp4)

## Features
- Full-screen style centered layout
- Animated transitions between slides
- Prev/Next controls (no external slider library)
- Overlay content (title, description, CTA button)

## Project Structure
- `imageSlider.html` - markup for the slider items and navigation buttons
- `imageSlider.css` - all styling and animations
- `imageSlider.js` - slide rotation logic (append/prepend)
- `assets/` - optional folder (project-dependent)
- `marvel/` - images referenced by the demo items

## How It Works
`imageSlider.js` rotates the slides by moving DOM elements:
- **Next**: `appendChild(items[0])` to move the first item to the end
- **Prev**: `prepend(items[last])` to move the last item to the front

The CSS uses `nth-child` selectors to position each slide and control which one is visible.

## Usage
1. Open `imageSlider.html` in a browser.
2. Click **Prev** / **Next** to change slides.

## Customization
- **Add/remove slides**: update the `.slide` container in `imageSlider.html` with more `.item` blocks.
- **Replace images**: change `style="background-image: url(./marvel/<file>.jpeg)"` for each item.
- **Update text**: edit `.name`, `.about`, and the button label inside each item.

## Notes
- This is a demo-style slider; for production you may want to:
  - generate slides dynamically
  - support keyboard/swipe interactions
  - add accessibility improvements (ARIA labels, focus handling)

