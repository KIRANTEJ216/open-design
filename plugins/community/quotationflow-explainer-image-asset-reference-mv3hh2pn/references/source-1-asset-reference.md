# QuotationFlow Explainer — Image Asset Reference

All four assets below are **reference images to generate and drop into the
HyperFrames composition** at `.hyperframes-cache/1786765850-quotationflow/index.html`.
Generate each in an image project (gpt-image-2 or flux-pro-ultra) at 1:1 unless
noted, then reference via CSS `background-image` or `<img src="...">` inside
the relevant scene.

---

## Asset 1 — S1 Opening Scene: Dark Tech/Mesh Background Texture
**Filename to save as:** `asset-s1-bg-texture.png`
**Aspect:** 16:9 · **Size:** 1920×1080

### Generation Prompt (gpt-image-2 / flux-pro-ultra)
```
Dark navy background with an ultra-subtle hexagonal circuit mesh pattern. 
Deep space navy color #0E1421 fills 95% of the canvas. Fine hairline grid 
lines form a precise hexagonal lattice at 5-8% opacity in cold electric 
purple-blue. Occasional faint node dots where grid lines intersect. 
Zero gradients. No glow, no lens flare, no people, no photography. 
Pure flat motion-graphic texture. SaaS tech aesthetic — precise, 
geometric, minimal. Like a PCB viewed from very far above. 1920×1080, 
widescreen 16:9.
```

### Usage Notes
- **Where:** S1 clip (`#s1`) as a CSS `background-image`
- **In CSS:**
  ```css
  #s1 { background: url('asset-s1-bg-texture.png') center/cover no-repeat, var(--navy); }
  ```
- **Opacity hint:** wrap in a div set to `opacity: 0.4` so the texture
  reads as depth without overpowering the type.
- **Licensing:** generate fresh via gpt-image-2 — you own the output.
  Do NOT source from stock sites; mesh textures on Shutterstock/Getty
  carry editorial-only licences when they include trademarked circuit
  designs.

### Fallback Generation Prompt (simpler, faster via DALL-E-3)
```
Abstract dark navy background. Fine white circuit board lines at 8% opacity, 
forming a sparse hexagonal grid. Flat 2D graphic. No people, no text, no photography.
```

---

## Asset 2 — S1 Logo Area: Stylised Transformer / Electrical Brand Icon
**Filename to save as:** `asset-vve-icon.png`
**Aspect:** 1:1 · **Size:** 512×512 (renders at 96×96 in video)

### Generation Prompt (gpt-image-2)
```
Flat vector-style icon: a stylised electrical transformer coil cross-section. 
Clean SaaS icon aesthetic. Deep purple-blue background square with 24px rounded 
corners, color #6B3FD8. Centered white illustration of a transformer toroidal 
coil — two nested rings with a vertical lightning bolt passing through the centre. 
Crisp lines, no gradients on the illustration itself. Icon size fills ~65% of 
the square. White on #6B3FD8 purple. Very clean, corporate tech feel. 
512×512 pixels.
```

### Usage Notes
- **Where:** Replaces the current inline SVG lightning bolt inside `#s1-logo-ring`
- **In HTML:**
  ```html
  <div id="s1-logo-ring">
    <img src="asset-vve-icon.png" width="64" height="64" alt="VVE" 
         style="border-radius: 8px;">
  </div>
  ```
- **Size in video:** the logo ring is 96×96px; render the icon at 512px and
  let the browser scale down for crisp Retina-quality rendering.
- **Alt prompt if transformer looks too technical:** try "stylised electric
  bolt encircled by two arcing wires, flat SaaS icon, white on deep purple,
  rounded square".

### Existing inline SVG (current fallback — keep this if generated icon
  doesn't match brand tone)
The existing SVG is a simple ⚡ lightning bolt in white on the purple gradient
box. It's serviceable; the generated icon is purely an upgrade if available.

---

## Asset 3 — S5 Invoice Scene: Premium PDF / Document Icon
**Filename to save as:** `asset-invoice-icon.png`
**Aspect:** 1:1 · **Size:** 512×512 (renders at ~180×200 in video)

### Generation Prompt (gpt-image-2)
```
Flat vector icon of a business invoice / PDF document. White document page 
with a folded corner at the top-right, 12px rounded corners on the bottom 
two corners. On the page: three thin horizontal lines representing text rows, 
a small table grid at the bottom, and a red PDF badge label in the top-left 
corner. Below the document, a clean green downward arrow in a circle 
indicating download. Colour palette: white document, #E0E0E0 line fills, 
#56CA00 green download circle, #E53935 PDF badge. Transparent or white 
background. 512×512. Ultra clean, minimal, corporate SaaS style.
```

### Usage Notes
- **Where:** S5 clip (`#s5`), next to the "Invoice Generated" text label
- **In CSS:**
  ```css
  #s5-doc-icon {
    width: 160px;
    height: 180px;
    background: url('asset-invoice-icon.png') center/contain no-repeat;
  }
  ```
- **Animation:** The existing GSAP tween `#s5-doc` does `y: 40, opacity: 0`
  entrance at t=21.0 — the icon can use the same clip wrapper.
- **Fallback:** The current composition draws the document outline in pure CSS.
  The generated asset replaces it for a more polished, print-ready look.

---

## Asset 4 — S6 Close Card: Dark Bokeh / Light-Leak Background
**Filename to save as:** `asset-s6-bokeh.png`
**Aspect:** 16:9 · **Size:** 1920×1080

### Generation Prompt (gpt-image-2 / flux-pro-ultra)
```
Premium cinematic dark background. Near-black navy #0A0D1A base. Soft 
out-of-focus bokeh circles: a few large blurred circles in deep purple 
#8C57FF at 25% opacity, scattered towards the top-left; two smaller 
amber-gold #FFB400 bokeh orbs at 15% opacity, bottom-right quadrant. 
Gentle vertical light-leak streak in violet on the far right edge at 8% 
opacity. No sharp edges, everything deeply blurred. No text, no objects, 
no people. Cinematic luxury product photography bokeh background. 1920×1080, 
16:9 widescreen.
```

### Usage Notes
- **Where:** S6 clip (`#s6`) as background layer beneath the wordmark/CTA
- **In CSS:**
  ```css
  #s6 { 
    background: url('asset-s6-bokeh.png') center/cover no-repeat, #0E1421; 
  }
  ```
- **Layering:** The existing `#s6-glow` radial gradient (purple ambient)
  can be removed once the bokeh image is in place — the bokeh image
  replaces both functions.
- **Opacity hint:** If the bokeh is too busy, add a semi-transparent dark
  overlay div above it: `background: rgba(10,13,26,0.55)` before the text
  content layers.
- **Licensing:** generate fresh via gpt-image-2 or flux-pro-ultra. You own
  AI-generated outputs. Bokeh images from Unsplash (license: free) are also
  acceptable — search "dark purple bokeh background" and use any
  Unsplash-licensed result.
  - Recommended Unsplash search: `dark purple bokeh business`
  - Ensure the image is dark enough (histogram skewed below 30% luminance)
    so white text contrast remains ≥ 7:1.

---

## Summary Table

| # | Filename | Scene | Aspect | Size | Model |
|---|---|---|---|---|---|
| 1 | `asset-s1-bg-texture.png` | S1 OPEN background | 16:9 | 1920×1080 | gpt-image-2 or flux-pro-ultra |
| 2 | `asset-vve-icon.png` | S1 logo ring | 1:1 | 512×512 | gpt-image-2 |
| 3 | `asset-invoice-icon.png` | S5 invoice document | 1:1 | 512×512 | gpt-image-2 |
| 4 | `asset-s6-bokeh.png` | S6 CLOSE background | 16:9 | 1920×1080 | gpt-image-2 or flux-pro-ultra |

## How to use after generating

1. Generate each asset in a new Image project (use gpt-image-2 for speed,
   flux-pro-ultra for highest quality on the backgrounds).
2. Download the files and copy them into this project's root:
   `/Users/kirantej/Library/Application Support/Open Design/namespaces/release-stable/data/projects/d183e3d1-520f-4d55-8e09-05260a069039/`
3. Edit `.hyperframes-cache/1786765850-quotationflow/index.html` with the
   CSS changes noted above.
4. Re-dispatch the render:
   ```bash
   "$OD_NODE_BIN" "$OD_BIN" media generate \
     --project "$OD_PROJECT_ID" \
     --surface video \
     --model hyperframes-html \
     --output "quotationflow-explainer-v3.mp4" \
     --composition-dir ".hyperframes-cache/1786765850-quotationflow"
   ```
