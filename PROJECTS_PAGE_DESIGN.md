# Projects Page Design

This document explains how the Hoobaan Construction Projects page is built now, what it contains, and how the project/about section should be understood when editing the page later.

## Page Purpose

The Projects page is the portfolio page for Hoobaan Construction Company. It shows real completed work, 3D architectural visuals, interior design examples, and one project video in a clean visual flow.

The page should help visitors quickly see:

- Completed building work.
- 3D visualization quality.
- Interior design and finishing quality.
- A clear standalone project video.
- Contact details and links back to the main website pages.

## Source File

The page is built in:

`Projects.html`

It is a static HTML page using Tailwind CSS from the CDN, custom CSS in the page head, GSAP/ScrollTrigger from CDN, and inline JavaScript near the bottom of the file.

## Brand System

The Projects page uses the Hoobaan brand palette:

- `brand.navy`: `#061E46`
- `brand.blue`: `#0A2C73`
- `brand.red`: `#B91C1C`
- `brand.dark`: `#041126`
- `brand.soft`: `#D6DEEA`

The visual direction is dark navy, white text, and red accents. The red color is used for section labels, active details, hover states, and small emphasis elements.

## Page Structure

The page currently has four main sections, plus the shared sticky navigation:

1. Hero section.
2. Video showcase section.
3. Hybrid project showcase.
4. Footer/contact area.

A lightbox component sits after the footer and opens when a video or gallery image is clicked.

## Navigation

The navigation matches the shared Hoobaan navbar style used across the website.

It contains:

- Logo image from `img/HomePage_photos/companyLogo.jpg`.
- Desktop links: Home, About, Services, Projects.
- Active Projects state with red text and a red underline.
- Desktop Contact Us button linking to `index.html#contact`.
- Mobile menu button with hamburger and close icons.
- Slide-in mobile menu with the same page links and Contact Us button.
- Overlay layer that closes the mobile menu when clicked.

Important IDs used by JavaScript:

- `mobile-menu-btn`
- `mobile-menu`
- `menu-overlay`
- `hamburger-icon`
- `close-icon`

These IDs should be preserved because the menu script depends on them.

## About The Projects Page

This page presents Hoobaan work as visual proof. The current headline says:

`Built Proof, Not Promises.`

The supporting Somali copy explains that visitors can view real projects, 3D designs, and the level of work delivered by Hoobaan Construction Company.

The content is intentionally visual-first. Completed building cards include short English back-side text that can be edited inside `projectImageGroups.completed.details`.

## Hero Section

The hero section uses the class:

`projects-hero`

It is a tall first screen with a background image, dark overlay, and strong typography.

Current hero content:

- Eyebrow label: `Mashaariicda Hoobaan`
- Main heading: `Built Proof, Not Promises.`
- Body copy: `Daawo mashaariic dhab ah, naqshado 3D ah, iyo heerka shaqo ee Hoobaan Construction Company ka fuliso dalka.`

Current hero media:

- Background image: `img/projects/building/building-01.webp`

The hero does not use a background video. The project video has its own section so people can see it clearly.

## Video Showcase

The video section uses the ID:

`project-video`

It contains one large native video player:

- Video source: `img/Videos/Hobaan G+1.mp4`
- Poster image: `img/projects/building/building-01.webp`

The video uses native controls and sits separately from the hero. This keeps the hero simple while allowing the project video to open clearly and beautifully.

## Projects Gallery

The gallery section has the ID:

`projects-gallery`

The gallery is a hybrid showcase. It does not use category tabs.

It contains three visible rows:

1. `Completed Buildings`
2. `3D Visuals`
3. `Interiors`

Completed Buildings use flip cards. 3D Visuals and Interiors use automatic infinite horizontal loops.

## Gallery Layout

Completed building cards use CSS 3D flip styling:

- `.project-flip-card`
- `.project-flip-inner`
- `.project-flip-front`
- `.project-flip-back`

The front side is image-first. The back side uses short English text that describes the image in a simple editable way.

3D Visuals and Interiors use:

- `.project-marquee-window`
- `.project-marquee-track`
- `.project-marquee-card`

The marquee renderer duplicates each image list once so the CSS animation can loop continuously.

Important gallery rules:

- Keep the front side of completed cards mostly image-only.
- Put completed project description text on the card back.
- Keep back text short, English, and easy to replace.
- Include every valid image in each category folder.
- Preserve the folder/file order when adding images to the JavaScript arrays.

## Gallery Content

The current gallery pulls images from the folders the user arranged under `img/Projects_photos/`.

### Completed Buildings

Folder:

`img/Projects_photos/Completed Projects/`

Current count:

- 18 images

### 3D Visuals

Folder:

`img/Projects_photos/3D visualization/`

Current count:

- 31 images

### Interiors

Folder:

`img/Projects_photos/Interior Design/`

Current count:

- 36 images

Hidden/system files such as `.DS_Store` are not gallery content.

## Footer And Contact

The Projects footer takes the same practical idea as the Home footer but uses a different layout.

It now contains:

- A project-focused CTA headline: `Mashruucaaga xiga ha yeesho muuqaal iyo tayo la hubo.`
- A WhatsApp action button for quick contact.
- Hoobaan brand block with logo and short Somali company statement.
- Navigation links for Home, About Us, Services, and the active Projects page.
- Thin separator lines between the brand text, page links, and contact sections.
- Contact details for location, phone numbers, email, Facebook, and TikTok.
- Icons beside the location, phone numbers, and email.

The footer should stay dark, clean, and project-focused. It should not be copied directly from the Home footer.

## Lightbox

The lightbox is a fixed overlay with the ID:

`lightbox`

It supports both image and video content.

Important IDs:

- `lightbox`
- `lightbox-img`
- `lightbox-video`
- `lightbox-caption`

Images open when a gallery card calls:

`openLightbox("image", imagePath, title)`

The lightbox can be closed by:

- Clicking the close button.
- Clicking the overlay outside the media.
- Pressing the Escape key.

When closing, the script pauses the video, removes media sources, hides the overlay, and unlocks body scrolling.

## JavaScript Behavior

The inline script handles these main behaviors.

### Mobile Menu

`toggleMenu()` opens and closes the mobile menu by toggling:

- `-translate-x-full` on the menu.
- `hidden` on the overlay.
- `hidden` on the hamburger and close icons.
- `overflow-hidden` on the body.

### Project Showcase Renderer

Gallery image paths are stored in:

`projectImageGroups`

The object has three keys:

- `completed`
- `visuals`
- `interiors`

`renderBuildingFlipCards()` creates the Completed Buildings flip-card grid from `projectImageGroups.completed.images` and `projectImageGroups.completed.details`.

`renderMarqueeGallery("visuals")` and `renderMarqueeGallery("interiors")` create duplicated image tracks for the automatic marquee loops.

### Lightbox

`openLightbox(type, src, title)`:

- Resets previous image/video state.
- Loads either image or video.
- Sets the caption.
- Shows the overlay.
- Locks body scroll.

`closeLightbox()` reverses that state.

## Animation

The page uses GSAP when available and when the user does not prefer reduced motion.

Current animations:

- Navbar slides/fades in on load.
- Hero text elements animate in with stagger.
- Video showcase animates on scroll.
- Project rows animate on scroll.
- Flip cards rotate smoothly on hover or tap.
- Marquee rows move continuously and pause on hover.

The custom CSS also respects reduced motion for gallery card transitions.

## Editing Rules

When updating the Projects page:

- Keep the dark premium construction style.
- Keep red as an accent, not the dominant color.
- Preserve the shared navbar sizing and mobile menu IDs.
- Keep `img/Videos/Hobaan G+1.mp4` as the standalone video showcase source.
- Do not use `img/Videos/testimonial.mp4` here because it belongs to the Home page.
- Keep gallery images under the current `img/Projects_photos/` category folders.
- Include all valid image files in each category folder.
- Do not include hidden/system files such as `.DS_Store`.
- Keep completed card back text short and editable.
- Keep the showcase hybrid: completed flip cards, 3D marquee, interiors marquee.

## Current Design Summary

The current Projects page is a four-part visual portfolio. It starts with a hero that uses text over a background image, then gives the project video its own large showcase section. The project showcase uses Completed Buildings as flip cards with short English back text, while 3D Visuals and Interiors move in continuous marquee strips. The footer keeps contact and navigation access available at the end of the page.
