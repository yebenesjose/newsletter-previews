# GitHub Pages Setup Instructions

## 1. Create the Repository

Go to https://github.com/new and create a new repository:
- **Name:** `newsletter-previews` (or your preference)
- **Visibility:** Private (or Public if you want easy sharing)
- **Do not** initialize with README

## 2. Push This Directory

```bash
cd /Users/yebenesjose/Desktop/Folders/DEV/WORK/claude/newsletter-wordtips/github-pages-site

git init
git add -A
git commit -m "Initial commit: CTA wireframes + email template previews"
git branch -M main
git remote add origin git@github.com:yebenesjose/newsletter-previews.git
git push -u origin main
```

## 3. Enable GitHub Pages

1. Go to **Settings → Pages** in the repo
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)`
4. Click **Save**

## 4. Access URLs

After a minute, your previews will be live at:

| Preview | URL |
|---------|-----|
| Landing | `https://yebenesjose.github.io/newsletter-previews/` |
| CTA Gallery | `https://yebenesjose.github.io/newsletter-previews/cta/` |
| Email Gallery | `https://yebenesjose.github.io/newsletter-previews/emails/` |

## Directory Structure

```
/
├── index.html              ← Landing page (links to both sections)
├── cta/                    ← CTA wireframe gallery
│   ├── index.html          ← Gallery with sidebar nav
│   ├── shared.css          ← Brand design tokens
│   ├── preview.css         ← Gallery layout styles
│   └── components/         ← 56 HTML component fragments
│       ├── atf/            ← Above-the-fold (16 states)
│       ├── mid/            ← Mid-content (12 states)
│       ├── btf/            ← Below-the-fold (12 states)
│       ├── future/         ← Exit-intent + conditional (14 states)
│       └── shared/         ← Buttons, inputs, toggles (12 states)
├── emails/                 ← Email template previews
│   ├── index.html          ← Gallery with sidebar nav
│   ├── connections-daily-hints.html
│   ├── welcome-01-orientation.html
│   ├── welcome-02-quick-win.html
│   ├── welcome-03-engagement.html
│   ├── post-solve-check.html
│   ├── reengagement-01-value-recap.html
│   ├── reengagement-02-puzzle-journey.html
│   └── reengagement-03-last-chance.html
└── SETUP.md                ← This file (delete after setup)
```

## Notes

- All email mockups use inline CSS (email-safe, no external dependencies)
- CTA gallery loads component fragments via fetch() — needs HTTP server (GitHub Pages works)
- For local preview: `python3 -m http.server 8080` from the root directory
