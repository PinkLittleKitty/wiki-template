---
title: Customizing Your Wiki
date: 2023-10-27 # Or current date
categories: [Template Guide, Configuration, Styling]
excerpt: Learn how to personalize your wiki's appearance, configuration, and layout.
---

# Customizing Your Wiki

This template is designed to be easily customizable. Here’s how you can tailor its appearance, configuration, and layout to fit your needs.

## Main Configuration (`_config.yml`)

The `_config.yml` file in the root of your project is the central place for site-wide settings.

Key settings to review and update:

```yaml
title: Your Wiki's Awesome Title
email: your-contact-email@example.com
description: >- # SEO description for your wiki
  A detailed and informative description of what your wiki is about.
baseurl: "" # Important: Set to "/your-repo-name" if hosted on GitHub Pages as a project site.
url: "https://yourdomain.com" # Your live website URL

author:
  name: Your Name or Organization
  # email: # Optional, if different from site email

# Wiki specific settings (if you add any custom ones)
wiki_options:
  show_last_updated: true
```

## Styling (SCSS)

The visual appearance of the wiki is controlled by SCSS files located in `assets/css/`. The main file you'll want to edit is `style.scss`.

### Key SCSS Variables

At the top of `assets/css/style.scss`, you'll find variables that control the core color scheme and fonts:

```scss
$primary-color: #3498db;   // Main theme color (links, accents)
$secondary-color: #2ecc71; // Secondary accent
$accent-color: #e67e22;    // For call-to-action buttons
$text-color: #333333;      // Main body text
$background-color: #f9f9f9; // Page background
$border-color: #e0e0e0;     // Borders
$font-family-sans-serif: -apple-system, BlinkMacSystemFont, "Segoe UI", /* ... */;
```

Change these values to match your desired branding. Jekyll will automatically recompile the SCSS into CSS when you save changes (if `jekyll serve` is running).

### Custom CSS Rules

You can add your own CSS rules directly into `style.scss` or create new `.scss` partials and import them.

## Layouts

The HTML structure of your pages is defined in the `_layouts` directory:

-   `default.html`: The main wrapper for all pages. Includes the `<head>`, site header, and footer.
-   `home.html`: The layout for your homepage (`index.md`).
-   `wiki.html`: The layout for individual wiki articles. This includes the sidebar, table of contents, and content area.

You can modify these HTML files to change the structure or add/remove elements. Be careful when editing, as changes can affect the entire site.

## Favicon

To change the favicon (the small icon in the browser tab):
1.  Create your favicon files (e.g., `favicon.ico`, `apple-touch-icon.png`, etc.).
2.  Place them in the `assets/images/` directory (or your preferred location).
3.  Update the links in the `<head>` section of `_layouts/default.html` to point to your new favicon files.

    ```html
    <link rel="icon" href="{{ '/assets/images/favicon.ico' | relative_url }}" type="image/x-icon">
    <!-- Add other favicon links as needed -->
    ```