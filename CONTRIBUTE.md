# Contributing to F5 AppWorld Lab Guides

This repository uses Hugo as the static site generator with reStructuredText (RST) for content.

## Prerequisites

Before contributing, ensure you have the following installed:

- **Hugo**: The static site generator. Install from [Hugo Installation Guide](https://gohugo.io/getting-started/installing/).
  ```
  brew install hugo
  ```

- **Docutils**: Required for RST processing.
  ```
  brew install docutils
  ```

## Writing Content

Content is written in RST format and placed in the `content/` directory.

### Frontmatter

Each content file must start with frontmatter, which provides metadata for Hugo.

Frontmatter can be in YAML, TOML, or JSON format. Hugo detects the format by the delimiters.

#### YAML Frontmatter
```
---
title: "Example Lab"
date: 23-09-2025
draft: false
---
```

#### TOML Frontmatter
```
+++
title = "Example Lab"
date = 23-09-2025
draft = false
+++
```

#### JSON Frontmatter
```
{
  "title": "Example Lab",
  "date": "23-09-2025",
  "draft": false
}
```

Common frontmatter fields:

- `title`: The page title.
- `date`: Publication date.
- `draft`: Set to true to exclude from build unless `--buildDrafts` is used.
- `weight`: For ordering pages.
- `description`: Page description.
- `keywords`: Array of keywords.
- `slug`: URL slug.
- `type`: Content type.

For a full list of options, see [Hugo Front Matter Documentation](https://gohugo.io/content-management/front-matter/).

Custom parameters can be added under `params`.

## Building and Testing

- To start a local server: `hugo serve`
- To build the site: `hugo`

For more on Hugo, visit [Hugo Documentation](https://gohugo.io/documentation/).

## Shortcodes

Hugo shortcodes are reusable snippets of content that can be embedded in your RST files. They allow you to add dynamic elements like call-outs, tabs, or custom components without repeating code.

To implement shortcodes, you need to define them in your theme or create custom ones. For examples, refer to the [nginx-hugo-theme's exampleSite](https://github.com/nginxinc/nginx-hugo-theme/tree/main/exampleSite/content/test-product).

### Running the Example Site

To see shortcodes in action and understand their usage:

1. Clone the nginx-hugo-theme repository:
   ```
   git clone https://github.com/nginxinc/nginx-hugo-theme.git
   ```

2. Navigate to the exampleSite directory:
   ```
   cd nginx-hugo-theme/exampleSite
   ```

3. Start the Hugo server:
   ```
   hugo serve
   ```

This will run the example site locally, where you can explore various shortcodes.

### Call-Outs Shortcode

A common shortcode is for call-outs, which highlight important information. Examples can be found in the `call-outs` folder of the exampleSite content: [exampleSite/content/test-product/call-out](https://github.com/nginxinc/nginx-hugo-theme/tree/main/exampleSite/content/test-product/call-out).

To use a call-out in your RST file, you might use something like:

```
{{< call-out type="note" >}}
This is a note.
{{< /call-out >}}
```

Check the [theme documentation](https://github.com/nginxinc/nginx-hugo-theme/blob/main/exampleSite/content/test-product/) for available shortcodes and their parameters.