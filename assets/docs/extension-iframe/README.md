# Iframe Extension

## Overview

The **Iframe** extension allows embedding of external content using the `<iframe>` HTML element. It supports setting attributes such as `src`, `width`, `height`, and more.

## Features

- Embed external content such as videos, websites, or maps.
- Customizable attributes like `src`, `width`, `height`, etc.
- Block-level content.
- Draggable and selectable.

## Attributes

| Attribute      | Description                                                    | Default   |
| -------------- | -------------------------------------------------------------- | --------- |
| `src`          | URL of the content to embed                                     | `null`    |
| `width`        | Width of the iframe element                                     | `600`     |
| `height`       | Height of the iframe element                                    | `400`     |
| `allow`        | Permissions for the iframe                                      | `null`    |
| `allowfullscreen` | Whether the iframe allows fullscreen mode                   | `false`   |
| `class`        | CSS classes to add to the iframe                                | `null`    |
| `id`           | ID attribute for the iframe                                     | `null`    |

## Commands

### `insertIframe`

Insert an `<iframe>` element into the editor.

```typescript
editor.commands.insertIframe({
    attrs: {
        src: 'https://example.com',
        width: '800',
        height: '600',
        allow: 'fullscreen',
        allowfullscreen: true,
        class: 'iframe-class',
        id: 'iframe-id',
    }
});
```

## Usage Example

```typescript
import { Button } from '@fusion/extension-button';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Iframe,
    /* other extensions */
  ],
});
```

## HTML Output Example
```html
<iframe src="https://example.com" width="800" height="600" allowfullscreen></iframe>
```
