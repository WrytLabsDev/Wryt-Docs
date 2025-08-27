# Meta Extension for Fusion Editor - @fusion/extension-meta

## Overview

The `Meta` extension allows you to insert `<meta>` tags within the Fusion Editor. Meta tags provide metadata about the HTML document, and this extension is useful for setting SEO information, character sets, or page settings.

## Features

- **Block Node:** Inserts `<meta>` tags as block-level nodes.
- **Command Integration:** Provides a command to insert meta tags with various attributes.
- **HTML Attributes:** Supports common `<meta>` attributes like `name`, `content`, `charset`, and `http-equiv`.

## Attributes

- **name:** The name of the metadata (e.g., "description").
- **content:** The content of the metadata (e.g., "A brief description").
- **charset:** The character encoding for the HTML document.
- **http-equiv:** Used to provide HTTP header information (e.g., "refresh").
- **id:** The unique identifier for the `<meta>` element.

## Commands

- **insertMeta:** Inserts a `<meta>` element with specified attributes.

## Configuration

### Default Configuration

- **Name:** `meta`
- **Block:** The extension is applied as a block node.
- **Parse HTML:** Recognizes `<meta>` tags and extracts their attributes when parsing HTML input.
- **Render HTML:** Outputs `<meta>` tags with any specified attributes.

## Customization

You can customize the `Meta` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Meta } from '@fusion/extension-meta';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Meta, /* other extensions */],
});
```

## HTML Output Example
```html
<meta name="description" content="A brief description" />
```