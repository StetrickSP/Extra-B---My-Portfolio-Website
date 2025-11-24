# Portfolio - Ngô Tấn Tài
Simple, responsive personal portfolio website built with plain HTML, CSS and a small JS helper.

## Overview
This project is a static portfolio site with pages for Home, About, Projects and Contact. It is intended as a lightweight, fast personal site showcasing skills, experience and projects.

## Pages / Structure
- `index.html` — Landing / Home section with intro, social links and CTA buttons.
- `about.html` — About, tech skills and work experience sections.
- `projects.html` — Projects, services and certifications.
- `contact.html` — Contact information and a simple contact form (static).
- `style.css` — All styles for the site.
- `script.js` — Small JS file used to toggle the mobile menu.
- `assets/` — Images, favicon and other static assets.

## Navigation bar
- Located in the header (`header.header`).
- Links are anchored to top-level pages and sections (`.navbar a`).
- `#menu-icon` + `.navbar.active` provides a simple mobile toggle:
  - `script.js` toggles `bx-x` on `#menu-icon` and `active` on `.navbar`.
  - Ensure CSS contains rules for `.navbar` and `.navbar.active` (show/hide on small screens).
- `button.gradient-btn` is a CTA button styled with a gradient.

## Responsiveness
- Viewport meta is set in every HTML file (`<meta name="viewport" content="width=device-width, initial-scale=0.75">`).
- Layout uses flexbox and CSS grid:
  - Sections like `.home`, `.about`, `.tech` rely on `display:flex`.
  - Images use responsive units (`vw`) so they scale with viewport.
- Recommended improvements:
  - Add media queries to stack columns and reduce gaps on tablets/phones.
  - Show `#menu-icon` on small screens and hide `.navbar` (desktop reverse).
  - Example:
    ```css
    @media (max-width: 900px) {
      #menu-icon { display:block; }
      .navbar { display:none; }
      .navbar.active { display:flex; flex-direction:column; }
    }
    ```
- Test on multiple viewports and devices; optimize image sizes for mobile.

## SEO & Accessibility
- Each page includes `<title>` and `<meta name="description">`.
- Use meaningful headings (`h1`, `h2`, `h3`) for content structure.
- All images include `alt` attributes — keep them descriptive.
- Add Open Graph / Twitter meta tags for better sharing:
  - `og:title`, `og:description`, `og:image`, `og:url`
- Add a sitemap and robots.txt for production to improve discoverability.
- Performance & SEO tips:
  - Compress/resize images in `assets/`.
  - Minify CSS and combine where possible.
  - Use `rel="preload"` for critical assets if needed.

## How to run locally
Simple open `index.html` in a browser for quick testing. To serve via a local static server:

- Using npm http-server:
  ```
  npm install -g http-server
  cd path/to/Extra-B
  http-server -c-1
  ```
- Or use Python (no install):
  ```
  # Python 3
  cd path/to/Extra-B
  python -m http.server 8000
  # then open http://localhost:8000
  ```

## File tree
```
Extra-B/
├─ index.html
├─ about.html
├─ projects.html
├─ contact.html
├─ style.css
├─ script.js
└─ assets/
   ├─ favicon.ico
   ├─ image.jpg
   ├─ tech-stack.png
   └─ project*.png
```

## Notes & Next steps
- Convert to responsive nav with accessible focus states and keyboard support.
- Add form handling (serverless endpoint or email service) for contact submission.
- Consider using a build step (minify CSS/images) for production deployment.
- Add analytics and verify sitemap/robots before publishing.
