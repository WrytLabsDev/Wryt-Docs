# Ins Extension for Fusion Editor - @fusion/extension-ins

## Overview

The `Ins` extension allows you to represent inserted text within the Fusion Editor. The `<ins>` tag is often used to mark new content that has been inserted into a document, making this extension useful for tracking document edits or changes.

## Features

- **Inline Node:** Renders the `<ins>` element as an inline node to represent inserted content.
- **Command Integration:** Provides commands to insert new content as an `<ins>` element.
- **Attributes:** Supports `cite` and `datetime` attributes for tracking insert origin and date.

## Attributes

- **cite:** Specifies a URL that explains the reason for the insertion.
- **datetime:** Specifies the date and time of the insertion.

## Commands

- **insertIns:** Inserts an `<ins>` element with the provided content and attributes.

## Configuration

### Default Configuration

- **Name:** `ins`
- **Group:** Inline
- **Inline:** The extension is applied as an inline node.
- **Atom:** The node behaves atomically.
- **Parse HTML:** Recognizes `<ins>` tags when parsing HTML input.
- **Render HTML:** Outputs `<ins>` tags with any additional HTML attributes.

## Customization

You can customize the `Ins` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Ins } from '@fusion/extension-ins';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Ins, /* other extensions */],
});
```

## HTML Output Example
```html
<p>This is <ins cite="https://example.com" datetime="2024-09-17T12:00:00Z">inserted text</ins>.</p>
```