# Personal Website

My personal website built with [Hugo](https://gohugo.io/).

## Development

```bash
# Start development server
hugo server

# Build static site
hugo
```

The development server runs at http://localhost:1313/ with live reload.

## Structure

```
├── content/           # Page content (Markdown)
├── data/              # Publications, patents, software (YAML)
├── layouts/           # HTML templates
├── static/            # Images, CSS, favicon
└── hugo.toml          # Site configuration
```

## Adding Content

**Publication:** Add entry to `data/publications.yaml`

**Patent:** Add entry to `data/patents.yaml`

**Software:** Add entry to `data/software.yaml`

## Deployment

Pushes to `main` automatically build and deploy via GitHub Actions.

### Setup

Add these secrets in GitHub repo settings → Secrets → Actions:

- `FTP_SERVER` - FTP hostname (e.g., `ftp.smartschat.de`)
- `FTP_USERNAME` - FTP username
- `FTP_PASSWORD` - FTP password
- `FTP_SERVER_DIR` - Remote directory (e.g., `/` or `/public_html/`)

### Manual

Run `hugo` to generate the static site in `public/`, then upload manually.
