# Paragraph Extension for Fusion Editor - extension-paragraph

## Overview

The `Paragraph` extension provides support for `<p>` elements in Fusion Editor. This extension allows you to create and manipulate paragraphs, which are fundamental for structuring text content in HTML. The extension is designed to integrate smoothly with other editor extensions and maintain a clean and semantic structure.

## Features

- **Standard Paragraph Support:** Enables the use of `<p>` elements to wrap and format blocks of text.
- **Customizable HTML Attributes:** Allows customization of HTML attributes for paragraphs.
- **Keyboard Shortcuts:** Provides a default keyboard shortcut for quickly setting paragraphs.

## Keyboard Shortcuts

- **Mod-Alt-0:** Sets the selected content or cursor position to a paragraph.

## Configuration

### Default Configuration

The `Paragraph` extension comes with sensible defaults that are suitable for most use cases. Here’s a breakdown of its configuration:

- **Name:** `paragraph`
- **Group:** `block` (Paragraphs are treated as block-level elements.)
- **Content:** `inline*` (Allows inline content, such as text, to be placed inside the paragraph.)
- **Parse HTML:** Recognizes `<p>` tags when parsing HTML input.
- **Render HTML:** Outputs `<p>` tags with any additional HTML attributes.
- **Priority:** `1000` (Ensures that the paragraph extension takes precedence in scenarios with potential conflicts.)

### Example

Here’s an example of how to use the `Paragraph` extension:

```typescript
import { Paragraph } from './path/to/your/paragraph-extension';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Paragraph, /* other extensions */],
});
```

### HTML Output
```HTML
<p>This is a paragraph of text.</p>
```

