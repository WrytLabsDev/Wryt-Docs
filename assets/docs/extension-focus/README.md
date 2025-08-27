# Focus Extension - @fusion/extension-focus

The `Focus` extension adds a CSS class to nodes in the editor that are currently focused, with customizable depth options. This extension is useful for highlighting specific content when it is selected or in focus.

## Overview

This extension allows you to control the focus effect within your editor by applying a custom class to focused nodes. You can specify the focus mode to define which nodes get the class based on their depth.

## Features

- Adds a focus class to selected nodes in the editor.
- Supports focus modes:
  - **All**: Adds the focus class to all matching nodes.
  - **Deepest**: Adds the focus class only to the deepest nested node.
  - **Shallowest**: Adds the focus class only to the shallowest nested node.

## Options

| Option       | Type                   | Default       | Description |
|--------------|------------------------|---------------|-------------|
| `className`  | `string`               | `'has-focus'` | CSS class name applied to focused nodes. |
| `mode`       | `'all'` \| `'deepest'` \| `'shallowest'` | `'all'` | Determines the depth at which the focus class is applied. |

## Installation

To use the `Focus` extension, import it into your editor configuration:

```typescript
import { Focus } from 'path/to/focus-extension';
```

## Usage

- Add the Focus extension to the editor’s extensions with your preferred options:

```typescript
import { Focus } from 'path/to/focus-extension';

const editor = new Editor({
    extensions: [
        Focus.configure({
            className: 'is-focused', // Custom focus class
            mode: 'deepest',         // Focus mode: 'all', 'deepest', or 'shallowest'
        }),
        // other extensions
    ],
});
```

## Example CSS for Focused Nodes

- Add styling to the focus class using CSS to customize the appearance of focused nodes:

```css
/* Refined Focus Styles */
.has-focus {
    position: relative;
    padding: 5px;
    border-radius: 5px;
    outline: none;
    transition: box-shadow 0.2s ease-in-out, transform 0.15s ease-in-out;
    box-shadow: 0 0 0 1px var(--purple), 0 0 6px rgba(128, 0, 128, 0.3);
}

body:not(.dark) .has-focus {
    box-shadow: 0 0 0 1px var(--purple), 0 0 8px var(--focus-glow-light);
}

body.dark .has-focus {
    box-shadow: 0 0 0 1px var(--purple), 0 0 8px var(--focus-glow-dark);
}

.has-focus:active {
    transform: scale(0.98);
}

```
