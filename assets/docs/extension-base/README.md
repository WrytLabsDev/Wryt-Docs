# Base Extension for Fusion Editor - @fusion/extension-base

## Overview

The `Base` extension provides support for the `<base>` element in Fusion Editor. The `<base>` element is used to specify a base URL and a default target for all relative URLs in a document. This extension allows you to define and manipulate the `<base>` element within your editor setup.

This extension is ideal for documents that require a base URL setting, particularly in environments where multiple relative links need to be aligned with a single base URL. The base tag is typically used in the <head> of an HTML document.

## Features

- **Base URL Support:** Allows the use of the `<base>` element to define a base URL for relative links in the document.
- **Customizable HTML Attributes:** Supports `href` and `target` attributes with customization options.
- **Non-Selectable Node:** The `<base>` element is non-selectable, maintaining its structural role without direct user interaction.

## Attributes
- **href:** Specifies the base URL for all relative URLs in the document.
- **target:** Specifies the default target for all hyperlinks and forms.

## Configuration

### Default Configuration

- **Name:** `base`
- **Group:** `block` (though it doesn't render visible content, it's treated as a block-level element for structural reasons)
- **Atom:** `true` (treated as an atomic node, meaning it can’t have child nodes)
- **Selectable:** `false` (not selectable in the editor)
- **Defining:** `true` (defines a unique identity within the document)
- **Parse HTML:** Recognizes the `<base>` tag when parsing HTML input.
- **Render HTML:** Outputs a `<base>` tag with any additional HTML attributes.
- **Priority:** `1000` (Ensures that the base extension takes precedence in scenarios with potential conflicts.)

### Example

```typescript
import { Base } from '@fusion/extension-base';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Base, /* other extensions */],
});
```

### HTML Output

```html
<base href="https://example.com/" target="_blank">
```

