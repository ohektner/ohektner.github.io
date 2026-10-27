# Owen Hektner — Portfolio

Personal site. Live at [ohektner.github.io](https://ohektner.github.io). Moved from ohek54/Portfolio in October 2026;
the old address forwards here from the `ohek54/ohek54.github.io` repo.

## Stack

- One `index.html`: plain HTML, CSS and JavaScript. No framework, no build step.
- Hosted on GitHub Pages (deploys from `main` about a minute after a push).
- Font: Onest (SIL Open Font License), self-hosted in `fonts/`.
- Hero animation: a canvas "signal" of stacked lines that follows the mouse and flattens on scroll. Drawn as a still frame for anyone with reduced motion turned on.
- Scroll reveals: CSS scroll-driven animations (`animation-timeline: view()`). Browsers without support just show the page as-is.

## Structure

```
index.html            # the whole site
favicon.svg
fonts/onest-latin.woff2
media/
  Owen_Hektner_Resume.pdf      # made with career-ops (output/cv-owen-hektner-general-*.pdf)
  og-image.jpg                 # link preview, 1200x630
  portrait-2026*.webp
  touch-dirt-home*.webp, touch-dirt-phone*.webp, touch-dirt-logo.webp
  cork-barrel-dashboard*.webp, nba-dashboard*.webp
```

Images come in two sizes (`-480`, `-720`, etc. for phones and 1x screens); `srcset` picks the right one.
The older files in `media/` (healthcare-*, liquor-*, nba-1/2, portrait.jpg) are no longer used by the page.

## Updating

Edit `index.html` or swap files in `media/`, then:

```bash
git add .
git commit -m "your message"
git push
```

## Checks run before the 2026-10 redesign shipped

- axe (WCAG 2.2 AA) at desktop and phone width: 0 issues
- Lighthouse (local): mobile performance 99, desktop 100; best practices 100; SEO 100.
  Accessibility reads 96 only because Lighthouse doesn't scroll, so it sees below-the-fold text
  in its faded "waiting to reveal" state. Once scrolled, contrast is full.
- No horizontal scroll at 390, 820 or 1440 px; all images and links resolve.
