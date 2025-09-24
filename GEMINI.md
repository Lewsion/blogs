# Gemini Code Assistant Context

## Project Overview

This is a Jekyll-based blog using the "Chirpy" theme. The blog is located at [https://blog.lewsion.com](https://blog.lewsion.com). The content is primarily focused on technical tutorials and documentation related to Docker, Ubuntu, Debian, and other technologies. The site is configured for Google Analytics, GoatCounter, and Giscus for comments. It also has PWA (Progressive Web App) features enabled.

## Building and Running

This is a Jekyll project. To build and run the project locally, you would typically use the following commands:

```bash
# Install dependencies
bundle install

# Serve the site locally
bundle exec jekyll serve
```

**Note:** These commands are inferred from the Jekyll documentation and the project structure. There are no explicit build scripts in the repository.

## Development Conventions

* **Content:** Blog posts are written in Markdown and stored in the `_posts` directory.
* **Front Matter:** Each post includes front matter with metadata such as `title`, `description`, `date`, `categories`, `tags`, and `author`.
* **Permalinks:** The permalink structure for posts is `/posts/:title/`.
* **Static Files:** Images and other static assets are stored in the `assets` directory.
* **Tabs:** The `_tabs` directory contains markdown files for the main pages of the site like "about", "archives", etc.

## Key Files

* `_config.yml`: The main configuration file for the Jekyll site. It contains settings for the theme, site metadata, analytics, comments, and more.
* `_posts/`: This directory contains the blog post files in Markdown format.
* `_tabs/`: This directory contains the main pages of the site.
* `assets/`: This directory contains static assets like images, CSS, and JavaScript.
* `index.html`: The main entry point for the site.
* `README.md`: Contains information about the Chirpy starter template.
