# Image Slider (Vanilla JS) — Documentation

## Overview
This project is a simple, library-free image slider built using **HTML + CSS + Vanilla JavaScript**.

It uses:
- **DOM reordering** (append/prepend) in `imageSlider.js` to rotate slides.
- **CSS `nth-child` rules** in `imageSlider.css` to position slides and control which one is “active”.
- **Overlay content** (title, description, CTA button) placed inside each slide item.

---

## Demo / Preview
Open:
- `frontend/spireX/imageSlider/imageSlider.html`

in any browser.

---

## Files
- **`imageSlider.html`**
  - Contains the slider layout.
  - Contains the slide items (`.item`) inside the `.slide` container.
  - Includes prev/next buttons.

- **`imageSlider.css`**
  - Responsible for layout, sizing, transitions, and animations.
  - Positions items using `nth-child()` selectors.

- **`imageSlider.js`**
  - Handles prev/next click events.
  - Rotates slides by moving DOM nodes.

- **`marvel/` (demo images)**
  - Folder containing the example images referenced by each slide.

---

## How the slider works
### 1) Prev / Next logic (JavaScript)
`imageSlider.js` “rotates” slides by reordering the `.item` elements inside `.slide`.

- **Next**:
  - Moves the first item to the end:
  - `appendChild(items[0])`

- **Prev**:
  - Moves the last item to the front:
  - `prepend(items[items.length - 1])`

Since the DOM order changes, the CSS `nth-child(...)` positioning updates what appears as the main/active slide.

### 2) Positioning and overlay (CSS)
`imageSlider.css` uses `nth-child` selectors to place items:
- `nth-child(1)` and `nth-child(2)` are treated as the primary slides (full container sizing).
- `nth-child(3..5)` are positioned progressively further to the right.
- `nth-child(n + 6)` are pushed out of view and set to low opacity.

Overlay text/button visibility is controlled by:
- `.slide .item:nth-child(2) .content { display: block; }`

So whichever slide becomes the 2nd child after rotation will show its overlay content.

---

## Customization
### Add a new slide
1. Edit `imageSlider.html`.
2. Inside the `.slide` container, add another `.item` block with:
   - `style="background-image: url(./marvel/<your-image>)"`
   - inner markup:
     - `.content`
     - `.name`
     - `.about`
     - `button`

### Replace images
Update each slide’s background image URL in `imageSlider.html`:
- `style="background-image: url(./marvel/<file>.jpeg)"`

### Change overlay text
Update inside each `.item`:
- `.name`
- `.about`
- the button label text

---

## Optional production improvements
This is a demo-style slider. For production use, consider:
- Adding accessibility (ARIA labels on buttons, focus handling).
- Supporting keyboard navigation (ArrowLeft / ArrowRight).
- Adding swipe support for mobile.
- Preventing layout issues for different screen sizes (more responsive positioning rules).

---

## Quick Start
1. Make sure the referenced images exist in the `marvel/` folder.
2. Open `imageSlider.html` in a browser.
3. Use **Prev** / **Next** to rotate slides.

