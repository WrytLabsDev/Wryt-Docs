# Dropcursor Extension - @fusion/extension-dropcursor

The `Dropcursor` extension adds a drop cursor to your editor, which is a visual indicator line that appears between nodes when dragging and dropping content. This feature enhances the drag-and-drop experience by clearly showing where content will be placed.

## Overview

This extension integrates ProseMirror's `dropCursor` plugin into the Tiptap editor, allowing customization of the cursor’s color, width, and additional styling through a custom class.

## Features

- Displays a drop cursor line while dragging content.
- Customizable color, width, and CSS class for styling.

## Options

| Option      | Type                | Default        | Description                                                        |
|-------------|---------------------|----------------|--------------------------------------------------------------------|
| `color`     | `string`            | `'currentColor'` | Sets the color of the drop cursor line. Accepts any valid CSS color value. |
| `width`     | `number`            | `1`            | Sets the width of the drop cursor line in pixels.                   |
| `class`     | `string`            | `undefined`    | Adds a custom CSS class to the drop cursor, allowing additional styling. |

## Installation

To use the `Dropcursor` extension, import it into your editor configuration:

```typescript
import { Dropcursor } from 'path/to/dropcursor-extension';
```

## Usage

- Add the Dropcursor extension to the editor’s extensions:

```typescript
import { Dropcursor } from 'path/to/dropcursor-extension';

const editor = new Editor({
    extensions: [
        Dropcursor.configure({
            color: 'red',   // Set custom color
            width: 2,       // Set custom width
            class: 'drop-cursor', // Add custom CSS class
        }),
        // other extensions
    ],
});
```

## Example CSS for Drop Cursor

- To style the drop cursor with a custom class, you can add the following CSS:

```css
/* Custom styling for the drop cursor */
.drop-cursor {
    background-color: rgba(255, 0, 0, 0.5); /* semi-transparent red */
    border-radius: 2px;
}
```

