# Contributing to F5 AppWorld Lab Guides

This repository uses Hugo as the static site generator with Markdown (md) for content.

Live examples of the following content can be viewed at the [nginx-hugo-theme exampleSite](https://nginxinc.github.io/nginx-hugo-theme/test-product/).

## Prerequisites

Before contributing, ensure you have the following installed:

**Hugo**: The static site generator. Install from [Hugo Installation Guide](https://gohugo.io/getting-started/installing/).
```
brew install hugo
```

## Writing Content

Content is written in markdown format and placed in the `content/` directory.

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

Hugo shortcodes are reusable snippets of content that can be embedded in your Markdown files. They allow you to add dynamic elements like call-outs, tabs, or custom components without repeating code.

You can view all Hugo's default shortcodes in their [documentation](https://gohugo.io/content-management/shortcodes/#article).

The following are all callouts supported by the [nginx-hugo-theme](https://github.com/nginxinc/nginx-hugo-theme) and can be viewed in the [exampleSite](https://github.com/nginxinc/nginx-hugo-theme/tree/main/exampleSite/content/test-product).

Live examples can be found at the hosted [exampleSite](https://nginxinc.github.io/nginx-hugo-theme/test-product/).

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

### Callouts

```
{{< call-out title="Call-out!" >}}
This is a plain callout with a custom title. Different callouts such as `important`, `caution` and `warning` differ in color and use their corresponding names instead of `call-out`.
{{</ call-out >}}
```

```
{{< call-out sideline="true" >}}
This is a plain side callout with no title. It has a [link](#callouts) to a heading on this page.
{{</ call-out >}}
```

```
{{< call-out "warning" >}}
This is an example of a warning callout! 
{{</ call-out >}}
```

You can view more callouts, their parameters, and examples [here](https://github.com/nginxinc/nginx-hugo-theme/tree/main/exampleSite/content/test-product/call-out).

---

### Card sections

```
{{< card-section >}}
  {{< card title="Card Section" >}}
    Usually used for featured content.
  {{</ card >}}
{{</ card-section >}}
```

You can view more card sections, their parameters, and examples [here](https://github.com/nginxinc/nginx-hugo-theme/blob/main/exampleSite/content/test-product/cards/permitted.md).

---

### Tables

```
{{< table >}}

| Type                     | Description                                                                          |
| ------------------------ | -------------------------------------------------------------------------------------|
| `plain`                  | A pure markdown table, will have the default attributes of `narrow` and `borderless`.|
| `shortcode`              | Wrapping a table with the `table` shortcode allows for the use of variant and theme. The `variant` parameter can be set to `narrow` or `wide`, while the `theme` parameter can be set to `bordered` or `borderless`.|
| `examples`               | Examples for all of these can be found at in the [variations.md](https://github.com/nginxinc/nginx-hugo-theme/blob/main/exampleSite/content/test-product/tables/variations.md?plain=1)|

{{</ table >}}
```

You can view more about tables, including examples, [here](https://github.com/nginxinc/nginx-hugo-theme/tree/main/exampleSite/content/test-product/tables).

---

### Tab groups

Tab groups can be useful for showcasing steps for different platforms, such as installation via Windows vs macOS.

You can view more tab group examples [here](https://github.com/nginxinc/nginx-hugo-theme/blob/main/exampleSite/content/test-product/tab-group/tab-group.md?plain=1).

```
{{< tabs name="Tab Group Example" >}}

{{%tab name="Windows"%}}

- **Hugo**: The static site generator. Install from the [Hugo Installation Guide](https://gohugo.io/getting-started/installing/).
  \`\`\`bash
  choco install hugo-extended
  \`\`\`

{{%/tab%}}

{{%tab name="macOS"%}}

- **Hugo**: The static site generator. Install from the [Hugo Installation Guide](https://gohugo.io/getting-started/installing/).
  \`\`\`bash
  brew install hugo
  \`\`\`

{{%/tab%}}

{{</ tabs >}}
```

-----

### Images

Images can be displayed using an `img` shortcode and can use the `grid` attribute to modify their size.

Note: do NOT start image paths with a leading slash (/) when you want them to respect the site's baseURL (for previews with a subpath). A leading slash makes the URL root‑relative and will drop any path component from baseURL.

For example when previewing a site with a img with `src="/F5_Logo.png"`, instead of `f5.com/appworld/labs/preview/path/F5_Logo.png` it will be linked to `f5.com/appworld/labs/F5_Logo.png`

```
{{< img src="F5_logo.png" grid="first-third" >}}
```
```
{{< call-out sideline="true" >}}
Sideline callouts also work with images!
{{</ call-out >}}
```

You can view more about image variables and examples [here](https://github.com/nginxinc/nginx-hugo-theme/blob/main/exampleSite/content/test-product/images/image-grid.md?plain=1).

-----

### Code Blocks

```md
Text inside a code block is copyable through a `Copy` button.
You can try it out with this code block!
```

More information and examples for code blocks can be found [here](https://github.com/nginxinc/nginx-hugo-theme/tree/main/exampleSite/content/test-product/code-blocks).
