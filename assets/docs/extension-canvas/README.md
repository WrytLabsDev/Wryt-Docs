# Canvas Extension for Fusion Editor - @fusion/extension-canvas

## Overview

The `Canvas` extension provides support for `<canvas>` elements in Fusion Editor. This extension allows you to create and manage canvas elements, which can be used for drawing graphics via scripting (usually JavaScript). The extension follows the technical summary and attributes defined for the `<canvas>` tag.

## Features

- **Canvas Element Support:** Enables the use of `<canvas>` elements for drawing graphics.
- **Customizable HTML Attributes:** Allows customization of HTML attributes for the canvas, such as `width`, `height`, etc.
- **Content Handling:** Although typically empty, the canvas element can have fallback content.
- **Keyboard Shortcuts:** Provides a default keyboard shortcut for toggling canvas elements.

## Technical Summary

### Content Categories

- **Flow content**: The canvas can be placed in places where flow content is accepted.
- **Phrasing content**: While typically empty, the canvas can contain fallback content.
- **Embedded content**: The canvas is considered embedded content.
- **Palpable content**: The canvas is perceivable by the user.

### Attributes

- **`width`**: Defines the width of the canvas in pixels. The default value is `300`.
- **`height`**: Defines the height of the canvas in pixels. The default value is `150`.

### Commands

- setCanvas: Creates a new canvas node with the specified attributes.
  ```typescript
    editor.commands.setCanvas({ width: '500', height: '300' });
  ```
- toggleCanvas: Toggles the canvas node on or off.
  ```typescript
    editor.commands.toggleCanvas({ width: '500', height: '300' });
  ```
- unsetCanvas: Removes the canvas node.
  ```typescript
    editor.commands.unsetCanvas();
  ```

## Configuration

### Default Configuration

The `Canvas` extension comes with sensible defaults that are suitable for most use cases. Here’s a breakdown of its configuration:

- **Name:** `canvas`
- **Group:** `block`
- **Content:** `inline*` (Allows inline content, such as text or other inline elements, as fallback content inside the canvas.)
- **Parse HTML:** Recognizes `<canvas>` tags when parsing HTML input.
- **Render HTML:** Outputs `<canvas>` tags with any additional HTML attributes.
- **Atom:** `true` (The canvas is treated as a self-contained element.)

### Example Usage

```typescript
import { Canvas } from '@fusion/extension-canvas';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Canvas.configure({ HTMLAttributes: { width: '500', height: '300' } }),
    /* other extensions */
  ],
});
```

### HTML Output

```html
<canvas width="500" height="300">Your browser does not support the canvas element.</canvas>
```