# Header Extension for Fusion Editor - @fusion/extension-header

## Overview

The `Header` extension provides support for the `<header>` element in Fusion Editor. This extension allows users to insert and manage header elements, which are typically used to introduce or group sections of a page or document.

## Features

- **Block-Level Element:** Inserts a `<header>` element, which can contain other block-level content.
- **Customizable HTML Attributes:** Allows customization of HTML attributes for the `<header>` tag.
- **Draggable:** Supports dragging the header block within the document.
- **Defining Node:** The header defines its own content, separating it from other blocks.

## Configuration

### Default Configuration

The `Header` extension provides customizable options with sensible defaults:

- **Name:** `header`
- **Group:** `block` (Headers are treated as block-level elements.)
- **Content:** `block*` (Can contain other block-level content.)
- **HTML Attributes:** `{}` (Custom HTML attributes can be added.)
- **Defining:** `true` (Indicates that the node defines its own structure.)

### Commands

- **insertHeader:** Inserts a new header block.
  ```typescript
  editor.commands.insertHeader();
  ```

## Usage

```typescript
import { Header } from '@fusion/extension-header';

const editor = new Editor({
  extensions: [
    Header.configure({
      HTMLAttributes: {
        class: 'custom-header-class',
      },
    }),
  ],
});
```

## HTML Output
```html
<header class="custom-header-class">
  <!-- Block-level content can go here -->
</header>
```
