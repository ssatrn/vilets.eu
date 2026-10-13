# snarv

A small, quiet personal website. Dark and icy by default, with a light theme for daytime. Three pages, no frameworks, no build step, and everything lives in a single file.

## What's in it

- **home**: a short intro, what you're up to right now, and a timeline of recent updates
- **notes**: a list of short writeups, grouped by year, where each note opens as its own page with back and next links
- **contact**: your email (with a copy button), a few links, and a form that opens the visitor's mail app

A few details worth knowing about:

- Dark and light themes. It follows the visitor's system setting at first, and the theme button in the sidebar overrides it and remembers the choice.
- A status bar along the bottom shows the current path (like `/home/snarv/notes`) and a clock.
- Works on phones. The sidebar collapses into a row of links across the top.
- Respects "reduce motion" settings, and the page heading gets keyboard focus when you switch pages.
- Prints cleanly. The sidebar, form and buttons are hidden in print.

## Files

```
index.html    the whole site: markup, styles and script
README.md     this file
```

The only thing loaded from outside is the JetBrains Mono font from Google Fonts. If it can't load, the page falls back to the visitor's system monospace font.

## Run it locally

Open `index.html` in any browser. No server or install needed.

## Make it yours

Open `index.html` in a text editor and search for these:

| What | Where |
| --- | --- |
| Your name | the `<title>`, the `brand` in the sidebar, the `h1` on home, the footer, and `/home/snarv` in the status bar and in the script (`var path`) |
| Intro text | the paragraph under the heading in the `home` section |
| "Right now" and "Lately" | the rows and timeline list in the `home` section |
| Email address | the `mailto:` link in the `contact` section. The copy button and the form both read the address from that link's text, so change both the link and its text |
| Contact links | the github and "elsewhere" rows in the `contact` section |
| Page description and share preview | the `description` and `og:` tags in the `<head>` |

### Colors

The palette is a handful of variables at the top of the `<style>` block:

```
--bg      page background
--panel   sidebar, status bar and form fields
--line    borders and dividers
--ink     body text
--bright  headings
--dim     secondary text
--ice     accent: links, highlights, active page
```

The light theme redefines the same variables twice, once for visitors whose system is set to light and once for the manual toggle. Keep the two blocks in sync when you change them.

### Font

The font is JetBrains Mono. To use another one, change the Google Fonts `<link>` in the head and the `font-family` rule on `body`.

## Adding a note

Each note needs two pieces, both inside the `notes` section:

1. A row in the list, under the right year. Pick a short slug with no spaces:

   ```html
   <div class="row" data-route="notes/my-slug">
     <dt>oct 20</dt>
     <dd><a href="#notes/my-slug" data-route="notes/my-slug">my note title</a><span class="tag">3 min</span></dd>
   </div>
   ```

2. The note itself, using the same slug:

   ```html
   <article data-note="my-slug" hidden>
     <h1>my note title</h1>
     <div class="note-meta">oct 20, 2026 &middot; 3 min read</div>
     <div class="note-body">
       <p>first paragraph.</p>
       <p>second paragraph.</p>
     </div>
   </article>
   ```

The back and next links are added automatically. "Next" follows the order the articles appear in the file, so put newer notes first if you want it to lead toward older ones.

## Adding a page

1. Copy one of the `<section data-page="...">` blocks and give it a new `data-page` name.
2. Add a matching link in the sidebar `nav`:

   ```html
   <li><a href="#about" data-route="about">about</a></li>
   ```

The page list is built from the sections, so nothing else needs changing.

## Publishing

It's a static page, so any static host works.

- **GitHub Pages**: put `index.html` in a repository, then turn on Pages in the repository settings.
- **Netlify or Cloudflare Pages**: drag the folder into the dashboard.
- **Any regular web host**: upload `index.html` to the site's root folder.

Pages are reached through the part of the address after the `#`, for example `yoursite.com/#notes/my-slug`, so no server setup is needed and links to individual notes work.

## Notes on privacy

There is no analytics, no tracking, and no cookies. The only saved data is the theme choice, kept in the visitor's own browser. The contact form sends nothing to any server. It just opens the visitor's own mail app with the message filled in.

## License

Add your own license here, or delete this section if you don't need one.
