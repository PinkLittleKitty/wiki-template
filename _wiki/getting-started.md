---
title: Getting Started with This Wiki Template
date: 2025-05-21
categories: [Template Guide, Setup]
featured: true
excerpt: Your first steps to setting up and using this Jekyll wiki template.
---

# Getting Started with This Jekyll Wiki Template

Welcome! This guide will walk you through setting up your own wiki using this Jekyll template.

## Introduction

This template provides a solid foundation for creating a clean, organized, and easy-to-navigate wiki. It includes features like a dynamic table of contents, category listings, and a customizable homepage.

## Installation

1.  **Clone or Download this Template:**
   ```bash
   git clone https://github.com/PinkLittleKitty/wiki-template your-new-wiki
   cd your-new-wiki
   ```

## Basic Configuration

The primary configuration file for your wiki is `_config.yml` located in the root of your project. Open it and customize these essential settings:

```yaml
title: My Awesome Wiki # The title that appears in the browser tab and site header
description: A brief description of your wiki for search engines and meta tags.
baseurl: "" # Important! If hosting on GitHub Pages as a project site (e.g., username.github.io/my-wiki), set this to "/my-wiki". Otherwise, leave it blank or as "/".
url: "" # Your site's full URL (e.g., "https://username.github.io" or "https://www.myawesomewiki.com")

# You can also update author details if you wish
author:
  name: Your Name
  email: your.email@example.com
```

For more details on customization, see the [[Customizing Your Wiki]] page.

### Custom Styling

You can customize the appearance of your wiki by editing the CSS files in the assets/css directory.

## Creating Wiki Pages

To create a new wiki page:

1. Create a new Markdown file in the _wiki directory -2. Add the required front matter:

```yaml
title: Your Page Title
date: YYYY-MM-DD
categories: [Category1, Category2]

```

Add your content using Markdown

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

## Next Steps: 

Once your basic setup is complete, you'll want to start adding your own wiki pages.

Learn how to create, structure, and categorize your content by reading our guide: [[Creating Wiki Pages & Content]].

## Troubleshooting

1. Double-check your _config.yml for any YAML syntax errors (indentation is key!).
2. Verify that your Markdown files have the correct front matter