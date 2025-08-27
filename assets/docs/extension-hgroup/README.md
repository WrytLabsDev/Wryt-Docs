
# HGroup Extension for Fusion Editor - @fusion/extension-hgroup

## Overview

The `HGroup` extension provides support for the `<hgroup>` element in Fusion Editor. This extension allows grouping of multiple heading levels, which is useful for sections with multiple subheadings, while maintaining the hierarchical structure of content.

## Features

- **Heading Group Support:** Allows grouping of multiple headings under a single `<hgroup>` tag.
- **Customizable HTML Attributes:** Supports the customization of HTML attributes for the `<hgroup>` element.
- **Keyboard Shortcuts:** Provides keyboard shortcuts to create an `<hgroup>` for ease of use.
- **Multi-Level Headings:** Combine headings like `<h1>` with `<h2>` or `<h3>` for grouped headings.
- **Markdown or Input Rules:** Supports markdown-like syntax for creating grouped headings.

## Configuration

### Default Configuration

The `HGroup` extension is configurable with these defaults:

- **Name:** `hgroup`
- **Group:** `block` (The `<hgroup>` is treated as a block-level element.)
- **Content:** `heading+` (Allows multiple heading levels such as `<h1>` and `<h2>` to be grouped.)
- **HTML Attributes:** `{}` (Allows for adding custom attributes like classes or IDs.)
- **Defining:** `true` (Indicates that the node is defining.)

### Commands

- **setHGroup:** Sets the content as an `<hgroup>` with multiple headings.
  ```typescript
  editor.commands.setHGroup({
    content: [
      { type: 'heading', attrs: { level: 1 } },
      { type: 'heading', attrs: { level: 2 } },
    ],
  });
  ```

- **toggleHGroup:** Toggles a selected block into an `<hgroup>` with headings.
  ```typescript
  editor.commands.toggleHGroup({
    content: [
      { type: 'heading', attrs: { level: 1 } },
      { type: 'heading', attrs: { level: 2 } },
    ],
  });
  ```

## Markdown or Input Rules

**Markdown Syntax:** Grouped headings can be generated using markdown-like syntax:
- Type `# Heading` followed by `## Subheading` and they can be grouped automatically under the `<hgroup>` tag when the command is triggered.

## Usage

```typescript
const editor = new Editor({
  extensions: [
    HGroup.configure({
      HTMLAttributes: { class: 'heading-group' },
    }),
  ],
});
```

## HTML Output

```html
<hgroup>
  <h1>Main Heading</h1>
  <h2>Subheading</h2>
</hgroup>
```

