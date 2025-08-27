# Embed Extension for Fusion Editor - @fusion/extension-embed

## Overview

The `Embed` extension allows users to insert and manage `<embed>` elements in the Fusion Editor. The `<embed>` element is used to embed external resources such as multimedia (e.g., audio, video) and plugins (e.g., PDFs) in the document.

## Features

- **Customizable HTML Attributes:** Supports attributes like `src`, `type`, `width`, and `height` for the embed element.
- **Block-level Node:** Treats the embed element as a block-level content, allowing it to be part of the document flow.
- **Draggable and Selectable:** Supports dragging and selecting the embed element within the editor.

## Configuration

### Default Configuration

The `Embed` extension can be configured with the following defaults:

- **Name:** `embed`
- **Group:** `block` (The embed element is treated as a block-level element.)
- **Attributes:**
  - `src`: The URL of the embedded resource (default: `null`).
  - `type`: The MIME type of the embedded content (default: `null`).
  - `width`: The width of the embedded content (default: `'600'`).
  - `height`: The height of the embedded content (default: `'400'`).

### Commands

- **insertEmbed:** Inserts an embed element at the current selection with the provided attributes.

```typescript
editor.commands.insertEmbed({
  src: 'https://example.com/sample.mp4',
  type: 'video/mp4',
  width: '800',
  height: '600',
});
```

## Usage
```typescript
const editor = new Editor({
  extensions: [
    Embed.configure({
      HTMLAttributes: {
        class: 'embed-responsive',
      },
    }),
  ],
});
```

## HTML Output
```html
<embed src="https://example.com/sample.mp4" type="video/mp4" width="800" height="600" />
```