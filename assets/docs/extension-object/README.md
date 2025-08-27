# `<object>` Extension for Fusion Editor

## Overview

The `<object>` extension allows you to embed objects, such as multimedia or interactive content, within your Fusion Editor. This extension supports various types of objects, providing a flexible way to include external content.

## Features

- **Embedding Objects**: Allows embedding various types of objects including images, videos, and interactive content.
- **Flexible Attributes**: Supports a range of attributes to customize the embedded object.
- **Fallback Content**: Provides fallback content if the object cannot be displayed.

## Attributes

- `data`: Specifies the URL of the object to embed.
- `type`: Defines the type of object being embedded (e.g., `image/jpeg`).
- `width`: Sets the width of the object.
- `height`: Sets the height of the object.
- `name`: Provides a name for the object.

## Commands

- To insert an `<object>` into your document, use the following command:

```typescript
editor.commands.insertContent({
  type: 'object',
  attrs: {
    data: 'https://example.com/object',
    type: 'image/jpeg',
    width: '600',
    height: '400',
    name: 'Sample Object'
  }
});
```

## Usage Example
```typescript
import { ObjectExtension } from '@fusion/extension-object';

const editor = new Editor({
  extensions: [
    ObjectExtension,
    // other extensions
  ],
});

```

## HTML Output Example

```html

<object data="https://example.com/object" type="image/jpeg" width="600" height="400" name="Sample Object">
  <!-- Fallback content -->
  <p>Your browser does not support the object tag.</p>
</object>

```