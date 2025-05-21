---
title: Getting Started
date: 2023-06-16
categories: [Guides, Tutorials]
featured: true
excerpt: Learn how to get started with our project with this comprehensive guide.
---

# Getting Started with Our Project

This is a sample wiki page that explains how to get started with our project.

## Introduction

Our project is designed to help you create beautiful and functional wikis using Jekyll. This guide will walk you through the basic setup and configuration.

## Prerequisites

Before you begin, make sure you have the following installed:

- [Ruby](https://www.ruby-lang.org/en/downloads/) (version 2.5.0 or higher)
- [RubyGems](https://rubygems.org/pages/download)
- [Bundler](https://bundler.io/)
- [Git](https://git-scm.com/)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/username/wiki-template.git
   cd wiki-template
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Start the local server:
   ```bash
   bundle exec jekyll serve
   ```

4. Open your browser and navigate to `http://localhost:4000`

## Configuration

The main configuration file is `_config.yml`. Here are some important settings:

```yaml
title: Your Wiki Title
description: Your wiki description
baseurl: "/your-repo-name"  # for GitHub Pages project sites
```

### Custom Styling

You can customize the appearance of your wiki by editing the CSS files in the `assets/css` directory.

## Creating Wiki Pages

To create a new wiki page:

1. Create a new Markdown file in the `_wiki` directory
2. Add the required front matter:
   ```yaml
   ---
   title: Your Page Title
   date: YYYY-MM-DD
   categories: [Category1, Category2]
   ---
   ```
3. Add your content using Markdown

## Advanced Features

### Categories

You can categorize your wiki pages by adding categories in the front matter:

```yaml
categories: [Documentation, Tutorials]
```

### Featured Pages

To mark a page as featured on the wiki home page, add this to the front matter:

```yaml
featured: true
```

## Troubleshooting

If you encounter any issues, try the following:

1. Make sure all dependencies are installed
2. Check your `_config.yml` for syntax errors
3. Verify that your Markdown files have the correct front matter

## Next Steps

Now that you have your wiki up and running, check out these resources:

- [Markdown Guide](https://www.markdownguide.org/)
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)