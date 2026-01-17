# Nil Painter

A Hugo-based artist portfolio and journal site for documenting painting trials, tribulations, and creative adventures.

## Site Structure

- **Homepage**: Gallery-style layout with latest posts and active collections
- **Blog**: Daily musings, progress updates, and creative adventures
- **Projects**: Individual art pieces with their own dedicated pages and update histories
- **About**: Artist information and contact

## Creating Content

### Creating a Blog Post

```bash
hugo new content/blog/my-post-title.md
```

Then edit the file and add your content:

```markdown
---
title: "My Post Title"
date: 2026-01-17
draft: false
---

Your post content here...
```

### Creating a New Project

```bash
hugo new content/projects/my-painting-project.md
```

Edit the file with project details:

```markdown
---
title: "My Painting Project"
date: 2026-01-17
draft: false
series: ["My Painting Project"]
---

## Concept

What inspired this piece...

## Challenge

What I'm trying to achieve...

## Materials

- Oil paints
- Canvas
- etc.
```

### Creating a Post Under a Project

Blog posts can be linked to projects using the `series` parameter:

```bash
hugo new content/blog/my-project-first-session.md
```

Edit the file and add the `series` parameter matching your project title:

```markdown
---
title: "My Painting Project: First Session"
date: 2026-01-17
draft: false
series: ["My Painting Project"]
series_order: 1
---

Today I started work on the underpainting...
```

**Important**: The `series` value must match the project's `series` value exactly (case-sensitive).

## Local Development

Start the Hugo dev server:

```bash
cd /home/fergal/development/nilpainter.github.io
hugo server -D
```

Visit http://localhost:1313 to preview your site.

## Building

Build the site:

```bash
hugo --gc --minify
```

## Deployment

The site automatically deploys to GitHub Pages when you push to the `main` branch via GitHub Actions.

```bash
git add .
git commit -m "Add new content"
git push
```

The site will be live at https://nilpainter.art in ~2 minutes.

## Content Tips

### Adding Images

Place images in `static/img/` and reference them in markdown:

```markdown
![Alt text](/img/my-image.jpg)
```

### Featured Images

Add a featured image to any post/project:

```markdown
---
title: "My Post"
image: "/img/featured.jpg"
---
```

### Header Images

The homepage hero image can be changed by replacing `static/img/header.jpg`.

### Drafts

Set `draft: true` in the front matter to hide content until it's ready:

```markdown
---
title: "Work in Progress"
draft: true
---
```

Use `hugo server -D` to preview drafts locally.

## Project Structure

```
nilpainter.github.io/
├── content/
│   ├── blog/          # Blog posts
│   ├── projects/      # Project pages
│   └── about.md       # About page
├── layouts/           # Custom templates
│   ├── blog/
│   ├── projects/
│   └── partials/
├── assets/
│   └── css/
│       └── schemes/
│           └── custom.css  # Custom styling
├── static/
│   └── img/          # Images
└── config/
    └── _default/
        ├── hugo.toml
        ├── params.toml
        └── menus.toml
```

## Customization

### Colors

Edit `assets/css/schemes/custom.css` to change the color scheme.

### Navigation

Edit `config/_default/menus.toml` to add/remove navigation items.

### Site Settings

Edit `config/_default/params.toml` for site-wide settings.

## Theme

Built with [Blowfish](https://blowfish.page/) theme, heavily customized for an elegant gallery aesthetic.
