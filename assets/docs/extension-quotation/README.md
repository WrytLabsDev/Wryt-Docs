# Q Extension for Fusion Editor - @fusion/extension-q

## Overview

The `Q` extension allows you to create inline quotations within the Fusion Editor. This is particularly useful for citing short passages of text or adding inline quotes to your content.

## Features

- **Inline Node:** Renders the `<q>` element as an inline node to represent inline quotations.
- **Command Integration:** Provides a command to set or toggle the `<q>` node.
- **Custom HTML Attributes:** Allows customization of the HTML attributes for the `<q>` element.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<q>` element using the `HTMLAttributes` option.

## Commands

- **setQ:** Inserts or toggles the `<q>` node in the editor.
```typescript
editor.commands.setQ();
```

## Configuration

### Default Configuration

- **Name:** q
- **Inline:** The extension is applied as an inline node.
- **Parse HTML:** Recognizes <q> tags when parsing HTML input.
- **Render HTML:** Outputs <q> tags with any additional HTML attributes.

## Usage Example

```typescript
import { Q } from '@fusion/extension-q';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Q, /* other extensions */],
});
```

### HTML Output Example
```html
<p>This is an example of an <q>inline quotation</q>.</p>
```