# Style Extension for Fusion Editor - @fusion/extension-style

## Overview

The Style extension for Fusion Editor allows you to embed `<style>` elements within the editor content. This is particularly useful for adding custom styles directly in the document or within a specific scope.

## Features

- Embed `<style>` elements in the editor content.
- Supports all global attributes.
- Allows for the addition of custom CSS rules.

## Attributes

- `HTMLAttributes`: An object to define HTML attributes for the `<style>` element.
  - Default: `{}`

## Commands

- **setStyleBlock:** Inserts a `<style>` block with the provided content.

```typescript
editor.commands.setStyleBlock({ content: 'body { background-color: black; }' });
```

## Usage
```typescript
import { Style } from '@fusion/extension-style';

const editor = new Editor({
  extensions: [
    Style.configure({
      HTMLAttributes: {
        id: 'main-style',
      },
    }),
    /* other extensions */
  ],
});
```

## HTML Output Example

```html
<style id="main-style">
  h1 { color: red; }
</style>

```
