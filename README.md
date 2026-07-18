# Metro Admin Template — dacheborede

A static Metro-style admin/dashboard UI template built with Bootstrap, jQuery and a collection of front-end plugins. It provides demo pages (charts, calendar, file manager, tables, widgets, forms, etc.) and ships with the assets and plugin bundles used in the demos.

## Features
- Full static front-end admin template (no back-end required)
- Demo pages: charts, calendar, gallery, file-manager, forms, tables, messages, tasks, UI components, widgets
- Integrated plugins: FullCalendar, Flot charts, DataTables, elFinder (file manager), Gritter (notifications), Chosen (selects), and others
- Bundled assets: Bootstrap, jQuery, fonts (Glyphicons/FontAwesome), images / avatars
- Simple local preview (open in browser or serve with a static HTTP server)

## Included plugins / libraries (high level)
- jQuery (used across UI & plugins)
- Bootstrap (layout & components)
- FullCalendar (calendar widgets)
- Flot (charts)
- DataTables (tables)
- elFinder (file manager UI)
- Chosen (enhanced select inputs)
- Various UI helpers and polyfills (excanvas, gritter, imagesLoaded, etc.)

## Repository layout (important files)
```
index.html                # Demo shell / main entry
custom.js                 # Template-specific JS initialization and wiring
style.css                 # Template styles (overrides)
bootstrap.min.css         # Bundled Bootstrap
bootstrap.min.js          # Bundled Bootstrap JS
style-responsive.css      # Responsive helpers
style-forms.css           # Form styles

Demo pages:
  calendar.html
  chart.html
  gallery.html
  file-manager.html
  form.html
  login.html
  messages.html
  table.html
  tasks.html
  ui.html
  widgets.html
  submenu*.html
  icon.html

Plugins / assets:
  fullcalendar.min.js
  jquery.elfinder.min.js
  jquery.dataTables.min.js
  jquery.flot.js
  jquery.gritter.min.js
  chosen.css, jquery.chosen.min.js
  excanvas.js
  many images: avatar*.jpg, bg-login.jpg, icons, buttons.gif
  font files: glyphicons*, fontawesome-*
```

## Quick start (local preview)
This is a static front-end. Some plugins work best when files are served over HTTP (XHR requests), so run a local server:

```bash
# clone
git clone https://github.com/mrawym636-sketch/dacheborede.git
cd dacheborede

# quick preview (Python 3)
python -m http.server 8000
# open http://localhost:8000/index.html in your browser
```

Or simply open `index.html` in your web browser for basic preview.

## How to customize
- Edit `index.html` to change the demo shell or swap which demo pages are linked.
- Add or change styles in `style.css` (or create a new custom CSS file and include it after `style.css`).
- Adjust UI behavior in `custom.js` (menu toggles, widget init code).
- Replace or remove demo images in the repository root (avatar*.jpg, bg-login.jpg) and update references in HTML/CSS.

## Notes & recommendations
- Many files in the repo are third-party libraries (minified bundles and fonts). If you plan to maintain this template long-term, consider:
  - Moving third-party libs into a `vendor/` or `libs/` folder.
  - Using a modern package manager/build flow (npm + webpack/Vite) for easier upgrades and smaller distribution.
  - Auditing which avatar images and font files you actually need and pruning unused assets to reduce repo size.
- Some legacy scripts (excanvas, old jQuery plugins) exist for IE support — they can be removed if you target modern browsers only.

## Troubleshooting
- If a plugin (eg. elFinder or FullCalendar) appears broken, serve files over HTTP (see Quick start) since some plugins make XHR calls that won't work from `file://`.
- If icons or fonts are not loading, verify the filenames in CSS and paths are correct.

## License
Check the original template or the project author for licensing details. The repo currently contains bundled third-party assets — respect each asset's license (e.g., FontAwesome/Bootstrap/etc.). Add a LICENSE file to the repository if you intend to publish under a specific license.

## Want help?
If you want, I can:
- Draft a smaller README with step-by-step setup and a short changelog.
- Produce a trimmed `assets/` structure (list of candidate files to remove).
- Create a minimal example that only includes Bootstrap + jQuery + the chart demo (`chart.html`) for easier integration.
