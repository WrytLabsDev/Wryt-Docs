# Heading Extension for Fusion Editor - @fusion/extension-heading

## Overview

The `Heading` extension provides support for `<h1>` to `<h6>` elements in Fusion Editor. This extension allows you to create and manage headings, which are essential for structuring content and indicating the hierarchy of information.

## Features

- **Multi-Level Headings:** Supports all six heading levels (`<h1>` to `<h6>`).
- **Customizable HTML Attributes:** Allows customization of HTML attributes for each heading level.
- **Keyboard Shortcuts:** Provides keyboard shortcuts for setting and toggling headings.
- **Input Rules:** Enables markdown-like syntax (`#`, `##`, etc.) to create headings.

## Configuration

### Default Configuration

The `Heading` extension is highly customizable with sensible defaults:

- **Name:** `heading`
- **Group:** `block` (Headings are treated as block-level elements.)
- **Content:** `inline*` (Allows inline content, such as text, within headings.)
- **Levels:** `[1, 2, 3, 4, 5, 6]` (Supports all heading levels.)
- **HTML Attributes:** `{}` (Custom HTML attributes for the headings.)
- **Defining:** `true` (Indicates that the node is defining.)

### Commands

- **setHeading:** Sets the content as a heading with a specified level.
  ```typescript
  editor.commands.setHeading({ level: 1 });
  ```

- **toggleHeading:** Toggles the content between a heading and a paragraph.

 ```typescript
editor.commands.toggleHeading({ level: 1 });
```

## Markdown or Input Rules

**Markdown Syntax:** Allows users to type `#` and `space` followed, that creates -> H1,

type `##` and `space` followed, that creates -> H2, etc., to create headings.

## Usage

```typescript
const editor = new Editor({
  extensions: [
    Heading.configure({
      levels: [1, 2, 3, 4, 5, 6],
    }),
  ],
});
```

## HTML Output

```html
<h1>This is a Heading Level 1</h1>
<h2>This is a Heading Level 2</h2>
<!-- up to h6 -->
 ```
