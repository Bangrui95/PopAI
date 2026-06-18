# POP_AI Single Page Website Design Specification

This document defines the visual and interaction rules for the POP_AI project introduction website. The site should present the project as a Pop Art-inspired AI image generation case study, combining bold visual impact with clear research storytelling.

## 1. Design Positioning

POP_AI is an experimental AI image generation project based on StyleGAN2-ADA and a custom Pop Art portrait dataset. The website should feel like:

- A Pop Art poster.
- An AI art research archive.
- A visual case study for dataset-driven image generation.
- A portfolio page with strong image-led storytelling.

The design should be expressive and high-contrast, but the content must remain readable and structured.

Core visual keywords:

- Pop Art
- AI-generated portrait
- Bold color
- Collage
- Poster visual
- Dataset process
- Experimental training

## 2. Page Structure

The website should be a single-page scrolling experience.

Recommended section order:

1. Hero
2. Project Overview
3. Dataset Preparation
4. Model Training Process
5. Generated Results
6. Experiment Reflection
7. Future Development

Each section should have one clear purpose. Avoid turning the page into a long technical report.

## 3. Color System

Use strong Pop Art colors with black outlines and high contrast.

```css
:root {
  --ink: #111111;
  --paper: #FAFAF5;
  --white: #FFFFFF;
  --hot-pink: #FF2D95;
  --pop-yellow: #FFD500;
  --cyan: #00C2FF;
  --electric-blue: #2F5BFF;
  --red: #F72525;
  --lime: #B8FF2C;
  --gray-100: #F2F2F2;
  --gray-300: #D8D8D8;
  --gray-700: #4A4A4A;
}
```

### Usage Rules

- Use `--paper` or `--ink` as the main page background.
- Use `--hot-pink`, `--pop-yellow`, `--cyan`, and `--red` as accent colors.
- Use black borders generously.
- Avoid soft pastel palettes.
- Avoid single-color dominance. The page should not become only pink, only blue, or only yellow.
- Use strong contrast between text and background.

Recommended combinations:

- Black text on paper background.
- White text on black background.
- Black text on yellow or cyan labels.
- White text on hot pink or electric blue blocks.

## 4. Typography

The typography should feel bold and poster-like for headings, but clean and readable for body text.

```css
:root {
  --font-display: "Arial Black", Impact, sans-serif;
  --font-body: Inter, Arial, Helvetica, sans-serif;
  --font-mono: "Space Mono", "Courier New", monospace;
}
```

### Type Scale

```css
h1 {
  font-family: var(--font-display);
  font-size: clamp(56px, 12vw, 150px);
  line-height: 0.9;
  letter-spacing: 0;
}

h2 {
  font-family: var(--font-display);
  font-size: clamp(36px, 6vw, 72px);
  line-height: 1;
  letter-spacing: 0;
}

h3 {
  font-family: var(--font-body);
  font-size: clamp(22px, 3vw, 32px);
  font-weight: 800;
  line-height: 1.1;
  letter-spacing: 0;
}

p {
  font-family: var(--font-body);
  font-size: 16px;
  line-height: 1.65;
}

.meta,
.tag,
.caption {
  font-family: var(--font-mono);
  font-size: 12px;
  line-height: 1.4;
}
```

### Typography Rules

- Use oversized display type only for the hero and major section titles.
- Body text should stay compact and readable.
- Do not use negative letter spacing.
- Keep letter spacing at `0`.
- Use monospace text for technical terms such as `StyleGAN2-ADA`, `FFHQ.pkl`, `512x512`, `tick 266`, and `kimg 1064`.

## 5. Layout Principles

The site should feel like a sequence of visual posters, not a generic template.

### General Layout

- Use full-width sections.
- Keep text columns around `560px` to `680px`.
- Use large images as rhythm breaks.
- Let images carry the visual weight.
- Use strong section contrast: paper section, black section, color section, gallery section.

### Grid

Recommended base layout:

```css
.section {
  padding: clamp(72px, 10vw, 140px) clamp(20px, 5vw, 72px);
}

.content-grid {
  display: grid;
  grid-template-columns: minmax(0, 0.9fr) minmax(0, 1.2fr);
  gap: clamp(28px, 5vw, 72px);
  align-items: center;
}

@media (max-width: 800px) {
  .content-grid {
    grid-template-columns: 1fr;
  }
}
```

### Section Rules

- Do not place every section inside a card.
- Use cards only for repeated items, short facts, or gallery captions.
- Do not nest cards inside cards.
- Keep border radius small: `4px` to `8px`.
- Prefer sharp, poster-like blocks over soft UI.

## 6. Hero Design

The hero should immediately communicate Pop Art and AI image generation.

Recommended hero asset:

- `IMAGE/333 final image.png`

Alternative assets:

- `IMAGE/333 final image2.png`
- `IMAGE/333 image com.png`

### Hero Requirements

- Use a full-bleed image background or large image-led composition.
- Title must be `POP_AI`.
- Supporting text should explain the project in one short sentence.
- Avoid placing hero text inside a card.
- Add a strong black or color overlay only if needed for readability.
- The next section should be slightly visible below the fold.

Suggested hero copy:

```text
POP_AI
A StyleGAN2-ADA experiment for Pop Art portrait generation.
```

## 7. Image System

Images are the main storytelling material. Use them deliberately.

### Recommended Asset Mapping

Hero:

- `IMAGE/333 final image.png`

Overview:

- `IMAGE/333 final image2.png`
- `IMAGE/333 image com.png`

Dataset:

- `IMAGE/F3.png`
- `IMAGE/FF.png`
- `IMAGE/22 download.png`
- `IMAGE/22 resize .png`
- `IMAGE/33 hand.jpg`

Training:

- `IMAGE/1 GAN2 ada.jpg`
- `IMAGE/1 GAN2 pkl.jpg`
- `IMAGE/11 first image.jpg`
- `IMAGE/111 training.png`
- `IMAGE/111 01.png`
- `IMAGE/111 06.png`

Generated Results:

- `IMAGE/333 final image.png`
- `IMAGE/333 final image2.png`
- `IMAGE/333 image com.png`
- `styleGAN2_ada_NVlabs/outputs/seed0000.png`
- `styleGAN2_ada_NVlabs/outputs/seed0001.png`
- `styleGAN2_ada_NVlabs/outputs/seed0002.png`
- `styleGAN2_ada_NVlabs/outputs/seed0003.png`
- `styleGAN2_ada_NVlabs/outputs/seed0004.png`
- `styleGAN2_ada_NVlabs/outputs/seed0005.png`

Reflection:

- `IMAGE/111. wenti.jpg`
- `IMAGE/111 wenti2.png`
- `IMAGE/60.png`
- `IMAGE/61.png`
- `IMAGE/62.png`
- `IMAGE/63.png`
- `IMAGE/64.png`
- `IMAGE/65.png`

### Image Treatment

Use thick borders and offset shadows.

```css
.image-frame {
  border: 4px solid var(--ink);
  box-shadow: 10px 10px 0 var(--hot-pink);
  background: var(--paper);
}

.image-frame.yellow {
  box-shadow: 10px 10px 0 var(--pop-yellow);
}

.image-frame.cyan {
  box-shadow: 10px 10px 0 var(--cyan);
}
```

### Image Rules

- Use real project images, not generic stock images.
- Compress large images before production use.
- Prefer `.webp` or optimized `.jpg` for large screenshots.
- Keep important final generated images high quality.
- Do not blur or darken images so much that the project result becomes hard to inspect.

## 8. Components

### Tags

Use tags for project metadata.

Suggested labels:

```text
STYLEGAN2-ADA
POP ART DATASET
FFHQ.PKL
512x512
CUSTOM TRAINING
IMAGE CLASSIFICATION
KIMG 1064
```

Tag style:

```css
.tag {
  display: inline-flex;
  align-items: center;
  min-height: 32px;
  padding: 6px 10px;
  border: 3px solid var(--ink);
  background: var(--pop-yellow);
  color: var(--ink);
  font-weight: 700;
}
```

### Buttons

Buttons should feel graphic and direct.

```css
.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 44px;
  padding: 0 18px;
  border: 3px solid var(--ink);
  background: var(--ink);
  color: var(--white);
  font-weight: 800;
  text-decoration: none;
  box-shadow: 6px 6px 0 var(--hot-pink);
}

.button:hover {
  background: var(--pop-yellow);
  color: var(--ink);
}
```

### Timeline

Use a simple timeline for the training process.

Recommended timeline points:

1. Image collection from Pinterest.
2. Resize images to `512x512`.
3. Sort Pop Art portrait dataset.
4. Test classifier and manual curation.
5. Try StyleGAN3 and review limitations.
6. Fine-tune StyleGAN2-ADA.
7. Compare WikiArt and FFHQ model directions.
8. Generate Pop Art portrait outputs.

Timeline style:

- Thick black line.
- Color blocks for each milestone.
- Short text only.
- Pair each milestone with one relevant image where useful.

### Gallery

The result gallery should feel like a collage.

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 12px;
}

.gallery-item {
  border: 4px solid var(--ink);
  background: var(--paper);
  overflow: hidden;
}

.gallery-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

Suggested pattern:

- Some images span 3 columns.
- Some images span 4 or 6 columns.
- Keep mobile layout as a simple 1 or 2 column grid.

## 9. Motion and Interaction

Use small, sharp interactions.

Recommended:

- Image hover: slight scale up.
- Button hover: color switch and shadow shift.
- Section reveal: subtle fade-up.
- Gallery image click: open larger preview.

Avoid:

- Heavy parallax.
- Long animated intros.
- Excessive glitch effects.
- Complex 3D scenes.
- Decorative gradient blobs.

Example:

```css
.gallery-item img {
  transition: transform 180ms ease;
}

.gallery-item:hover img {
  transform: scale(1.04);
}
```

## 10. Background and Decorative Elements

Decoration should reference Pop Art print language.

Allowed:

- Halftone dot texture.
- Black comic-style outlines.
- Color blocks.
- Offset shadows.
- Simple diagonal stripes.
- Collage-style image cuts.

Avoid:

- Soft glassmorphism.
- Blurry gradient orbs.
- Generic AI neon backgrounds.
- Overly polished SaaS-style cards.
- Beige or muted editorial styling.

Use decoration sparingly so the project images remain the focus.

## 11. Content Tone

The writing should be clear, direct, and reflective.

Tone:

- Confident
- Experimental
- Research-focused
- Visually descriptive
- Honest about limitations

Avoid making the site sound like a marketing landing page.

Suggested one-sentence overview:

```text
POP_AI explores how a custom Pop Art portrait dataset can fine-tune StyleGAN2-ADA to generate stylized AI poster visuals.
```

Suggested reflection sentence:

```text
The model began to capture Pop Art color and portrait structure, but limited training time and dataset scale still caused visual artifacts and unstable details.
```

## 12. Responsive Rules

Desktop:

- Use large hero type and full-width image sections.
- Use two-column text and image layouts.
- Use collage gallery layout.

Tablet:

- Reduce section spacing.
- Keep two-column layouts only where images remain readable.

Mobile:

- Stack all content in one column.
- Keep hero title large but not overflowing.
- Use 1 to 2 column galleries.
- Avoid tiny process screenshots if text inside them becomes unreadable.

Mobile example:

```css
@media (max-width: 640px) {
  .section {
    padding: 64px 20px;
  }

  h1 {
    font-size: clamp(54px, 22vw, 88px);
  }

  .gallery {
    grid-template-columns: repeat(2, 1fr);
  }
}
```

## 13. Accessibility

- Maintain strong contrast for all text.
- Do not put long text over visually busy images unless a readable overlay is added.
- Add meaningful `alt` text to images.
- Keep buttons at least `44px` high.
- Make gallery previews keyboard accessible if a lightbox is implemented.
- Do not rely on color alone to communicate section meaning.

## 14. Implementation Notes

Suggested static site structure:

```text
site/
├── index.html
├── styles.css
├── script.js
└── assets/
    ├── hero.webp
    ├── dataset/
    ├── process/
    ├── training/
    └── results/
```

Before building the final page:

1. Select 15 to 25 key images.
2. Copy selected images into `site/assets/`.
3. Compress large screenshots and generated images.
4. Write short section copy.
5. Build the page as a single static HTML site.

## 15. Design Checklist

Before final delivery, confirm:

- The first screen clearly says `POP_AI`.
- The hero uses a real generated project image.
- The page uses bold Pop Art colors without becoming visually chaotic.
- The dataset, training, results, and reflection sections are all present.
- Images are optimized enough for fast loading.
- Text is readable on desktop and mobile.
- Buttons, tags, and image frames follow the same visual system.
- The final page feels like a Pop Art AI project, not a generic portfolio template.

