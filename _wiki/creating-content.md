---
title: Creating Wiki Pages & Content
date: 2025-05-21
categories: [Template Guide, Content Creation]
excerpt: Learn how to add new pages, write content using Markdown, and organize your wiki.
---

# Creating Wiki Pages & Content

This guide explains how to add new pages to your wiki, write content using Markdown, and utilize features like categories and featured pages.

## Adding a New Wiki Page

All your wiki articles reside in the `_wiki` directory in the root of your project.

1.  **Create a New File:** Inside the `_wiki` directory, create a new file with the `.md` extension (e.g., `my-new-topic.md`). The filename will typically be used to generate the URL slug (e.g., `/wiki/my-new-topic/`).
2.  **Add Front Matter:** At the very top of your new Markdown file, you must include YAML front matter. This is metadata that Jekyll uses to process the page.

    ```yaml
    ---
    title: "My Awesome New Topic"
    date: YYYY-MM-DD # e.g., 2023-10-27
    categories: [CategoryName, AnotherCategory] # Optional, but recommended
    excerpt: "A short summary of this page, used in listings and search results." # Optional
    # featured: true # Optional: Add this if you want it on the homepage's "Featured" section
    ---
    ```

    *   `title`: The main title of your wiki page.
    *   `date`: The publication or last updated date.
    *   `categories`: A list of categories the page belongs to. This helps in organization and navigation.
    *   `excerpt`: A brief summary. If not provided, Jekyll might auto-generate one.
    *   `featured: true`: (Optional) Set this to `true` to potentially include this page in the "Featured Pages" section on the homepage (requires homepage layout to be configured to use this).

3.  **Write Your Content:** Below the front matter (after the closing `---`), write your content using Markdown syntax.

    ```markdown
    ---
    title: "Understanding Widgets"
    date: 2023-10-28
    categories: [Widgets, Concepts]
    ---

    # All About Widgets

    Widgets are an essential part of our system. Here's what you need to know...

    ## Types of Widgets

    There are several types:

    - Alpha Widgets
    - Beta Widgets
    - Gamma Widgets

    ## Configuring Widgets

    To configure a widget, you'll need to...
    ```

## Using Markdown

Markdown is a lightweight markup language with plain-text formatting syntax. Here are some basics:

-   **Headings:** `# H1`, `## H2`, `### H3`
-   **Bold:** `**bold text**` or `__bold text__`
-   **Italic:** `*italic text*` or `_italic text_`
-   **Lists:**
    -   Unordered: `- Item 1`, `* Item 1`
    -   Ordered: `1. Item 1`, `2. Item 2`
-   **Links:** `Link Text`
-   **Internal Wiki Links:** Use the `[[Page Title]]` syntax (e.g., `[[Getting Started with This Wiki Template]]`) or standard Markdown links `Link Text`. The `[[Page Title]]` syntax relies on the `jekyll-wikilinks` plugin if you have it, or you'll need to ensure your page titles match filenames for it to work with custom linking logic. For simplicity with this template, standard relative links are more robust: `Getting Started`.
-   **Images:** `!Alt Text` (ensure the image exists n the specified path)
-   **Code Blocks:**
    ```python
    def hello():
        print("Hello, Wiki!")
    ```

## Categories

Assigning categories helps users find related content. They are displayed on each wiki page and can be used to generate category index pages (if implemented).

## Featured Pages

As mentioned, adding `featured: true` to a page's front matter can highlight it on the homepage. The `home.html` layout in this template is set up to look for these.