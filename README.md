# Yu-Dev Documentation

This repository contains the documentation site for the Yu-Dev development team, built with [Hugo](https://gohugo.io/) and automatically deployed to GitHub Pages using GitHub Actions.

## 🚀 Quick Start

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) v0.146.0 or later
- Git

### Local Development

1. Clone the repository with submodules:
   ```bash
   git clone --recurse-submodules https://github.com/Ric2Dev/yu-dev.git
   cd yu-dev
   ```

2. Run the development server:
   ```bash
   hugo server -D
   ```

3. Open your browser and visit `http://localhost:1313`

### Building the Site

To build the static site:

```bash
hugo --gc --minify
```

The built site will be in the `public/` directory.

## 📁 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── hugo.yml          # GitHub Actions workflow for deployment
├── archetypes/               # Content templates
├── content/                  # Markdown content files
│   ├── docs/                 # Documentation pages
│   └── about/                # About pages
├── themes/
│   └── PaperMod/            # Hugo theme (git submodule)
├── hugo.toml                # Hugo configuration
└── README.md                # This file
```

## 📝 Adding Content

Create a new documentation page:

```bash
hugo new docs/your-page-name.md
```

Edit the created file in `content/docs/your-page-name.md` and set `draft: false` when ready to publish.

## 🚢 Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the `main` branch.

### Setup GitHub Pages

1. Go to your repository Settings > Pages
2. Under "Build and deployment", select "GitHub Actions" as the source
3. The workflow will automatically deploy on the next push to `main`

The site will be available at: `https://ric2dev.github.io/yu-dev/`

## 🎨 Theme

This site uses the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, installed as a git submodule.

## 📄 License

Coding and architecture definitions for the Yu-Dev development team.
