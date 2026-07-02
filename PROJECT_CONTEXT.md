# Hoobaan Construction Website - Working Context

Last updated: 2026-06-27

## Project Folder

Main workspace:

`/Users/yahye_hashi/Downloads/Hoobaan-construction copy`

Current main edited file:

`Projects.html`

## Current Page Focus

We are currently working on the Projects portfolio page for Hoobaan Construction Company.

The page uses:

- Tailwind CSS CDN
- GSAP + ScrollTrigger
- Hoobaan brand colors: dark navy, white, brick/red accent
- Somali + English copy
- Existing navbar/mobile menu IDs and behavior should not be broken

## Projects Page Current Direction

Projects page has been redesigned away from the old light filter-card layout.

Current structure:

- Hero section with text over a background image.
- Standalone video showcase using `img/Videos/Hobaan G+1.mp4`.
- Hybrid Projects showcase:
  - Completed Buildings as flip cards / flash cards.
  - 3D Visuals as an infinite horizontal marquee.
  - Interiors as an infinite horizontal marquee moving the opposite direction.
- Polished lightbox supports image and video viewing.
- Existing footer/contact area remains on Projects page.

Current gallery source folders:

- `img/Projects_photos/Completed Projects/`
- `img/Projects_photos/3D visualization/`
- `img/Projects_photos/Interior Design/`

Important Projects page rules:

- Do not use `img/Videos/testimonial.mp4` on Projects page; Home page already uses it.
- Do not use old incorrect `3D rendering` paths.
- Do not return the gallery to category tabs or static grids unless explicitly requested.
- Include every valid image file from each current category folder.
- Exclude hidden/system files such as `.DS_Store`.
- Completed card backs should use short English text that reflects the image and is easy to replace.
- Team On Site images are intentionally excluded from the Projects page for now.
- Preserve mobile menu IDs:
  `mobile-menu-btn`, `mobile-menu`, `menu-overlay`, `hamburger-icon`, `close-icon`

## Shared Navbar Rule

All four main pages now use the About page navbar sizing/style:

- `index.html`
- `about.html`
- `services.html`
- `Projects.html`

Keep navbar shell, logo, desktop links, contact button, and mobile menu dimensions consistent across all four pages. The navbar shell uses:

`h-20 max-w-7xl rounded-2xl px-4 sm:px-6 lg:px-7`

## Services Page Previous Notes

## Important Design Direction

Keep the page consistent with previous Hoobaan pages:

- Premium construction company style
- Dark navy blueprint/grid sections
- Red used as an accent only
- White text on dark backgrounds
- Clean lucide-style outline icons where icons are needed
- Avoid overly generic AI-looking layouts
- Avoid repeated rounded-card patterns when the user asks for more creative sections
- Use real construction imagery where possible

## Services Hero Current Intent

Hero section should:

- Use background image path exactly as written in the page:
  `img/services photos/serviceHeroImage.jpg`
- Keep headline:
  `Built With Precision.`
- Keep label:
  `Adeegyada Hoobaan`
- Make label sit closer to navbar/top area
- Make small body paragraph larger and more balanced
- CTA buttons should appear lower in the hero, after some scroll, before reaching the next section
- Hero CTA buttons use class:
  `hero-cta-actions`
- Hero section uses class:
  `services-hero`

Current GSAP behavior:

- Hero image scales in on load
- Hero text content animates in on load
- `.hero-cta-actions` reveals on scroll with ScrollTrigger:
  `start: "top+=260 top"`

## CTA Bottom Section Current Intent

Bottom CTA section is the dark rebar composition:

- Blue rebar texture on far left edge only
- Red rebar texture on far right edge only
- Center dark navy content area must dominate
- Headline should be 3 lines on desktop:
  `Ma rabtaa adeeg`
  `dhisme oo`
  `nadiif ah?`
- Paragraph should be broken so `qiyaaas, iyo...` starts on second line
- Buttons should be slightly narrower than before
- Red and blue diagonal lines should align with side image boundaries

Footer has been removed from this Services page.

## Image Path Rule

The user prefers keeping image paths exactly as written in the HTML, especially:

`img/services photos/...`

Do not rewrite paths to `assets/...` unless explicitly asked.

## Recent User Preference Notes

- User wants edits applied directly to the file when possible, not only code snippets.
- If the user asks for code only, provide just the replacement section.
- User often gives screenshot annotations and expects exact visual corrections.
