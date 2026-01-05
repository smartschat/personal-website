# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
# Development server with live reload (http://localhost:1313/)
hugo server

# Build static site to public/
hugo

# Build minified for production
hugo --minify
```

## Architecture

This is a Hugo static site for a personal academic/professional website.

### Data-Driven Content

Content for publications, patents, and software is stored in YAML files under `data/`:
- `data/publications.yaml` - Academic publications (title, authors, venue, links)
- `data/patents.yaml` - Patents (title, authors, assignee, id, date, url)
- `data/software.yaml` - Software projects, organized into `research` and `personal` sections

The `layouts/_default/list.html` template renders these data files based on the section (publications, patents, or software).

### Template Structure

- `layouts/_default/baseof.html` - Base template with HTML structure, includes nav partial
- `layouts/index.html` - Homepage template
- `layouts/_default/list.html` - Section list template with conditional rendering for each content type
- `layouts/partials/nav.html` - Navigation partial

### Content Pages

Markdown files in `content/` define page metadata and optional intro text. The actual list content comes from the YAML data files.

### Deployment

Pushes to `main` trigger GitHub Actions workflow (`.github/workflows/deploy.yml`) that builds with Hugo and deploys via FTPS. Requires FTP_SERVER, FTP_USERNAME, FTP_PASSWORD, and FTP_SERVER_DIR secrets.
