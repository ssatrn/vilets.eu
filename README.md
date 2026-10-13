# vilets.eu

A minimal personal website built around a simple idea: keep things quiet, personal, and useful.

**Live site:** [vilets.eu](https://vilets.eu)

## Overview

vilets.eu is a lightweight personal website for sharing a short introduction, recent activity, written notes, and contact information. It uses a restrained, typography-focused design with an icy accent palette, subtle interface details, and a dark-first aesthetic.

The project is built with vanilla HTML, CSS, and JavaScript, without a frontend framework or build tools.

## Features

- **Home page** — personal introduction, current activities, and a timeline of recent updates.
- **Notes** — short written pieces organized by year, with individual views and navigation between entries.
- **Contact page** — email, external links, and a contact form that opens the visitor's default email application.
- **Dark and light themes** — follows the visitor's system preference by default, with a manual toggle that remembers the selected theme.
- **Responsive layout** — adapts to smaller screens with a compact navigation layout.
- **Minimal interface** — monospace typography, subtle borders, an understated accent color, and a small status bar displaying the current route and time.
- **Accessibility considerations** — keyboard focus management, reduced-motion support, and print-friendly styles.
- **Privacy-conscious by design** — no analytics, third-party tracking, or cookies; the theme preference is stored locally in the browser.

## Tech Stack

- HTML5
- CSS3
- Vanilla JavaScript
- JetBrains Mono via Google Fonts
- GitHub Pages
- Custom `.eu` domain

## Project Structure

```text
vilets.eu/
├── index.html   # Website structure, styles, and logic
├── README.md    # Project documentation
└── CNAME        # Custom domain configuration
```

The website is intentionally self-contained. There are no framework dependencies, package installations, or compilation steps.

## Run Locally

Clone the repository:

```bash
git clone https://github.com/ssatrn/vilets.eu.git
cd vilets.eu
```

Open `index.html` directly in a browser. No local server or installation is required.

## Deployment

The site is hosted with GitHub Pages and served through the custom domain [vilets.eu](https://vilets.eu).

Updates are published by committing changes to the `main` branch and pushing them to GitHub. GitHub Pages then deploys the updated static site.

## Design Philosophy

The goal is to keep the experience lightweight and distraction-free. Typography, spacing, and small interface details do most of the work instead of large libraries, animations, or unnecessary components.

The result is a personal corner of the web that is easy to maintain, quick to load, and simple to extend.

---

Built and maintained by **ssatrn**.