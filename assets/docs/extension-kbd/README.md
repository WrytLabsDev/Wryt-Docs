# Kbd Extension for Fusion Editor - @fusion/extension-kbd

## Overview

The `Kbd` extension allows you to represent user keyboard input within the Fusion Editor. The extension is useful for technical writing, tutorials, and documentation where keyboard commands need to be highlighted.

## Features

- **Inline Node:** Renders the `<kbd>` element as an inline node to represent keyboard input.
- **Command Integration:** Provides commands to insert keyboard input as a `<kbd>` element.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<kbd>` element using the `HTMLAttributes` option.

## Commands

- **insertKbd:** Inserts a `<kbd>` element with the provided content.

## Configuration

### Default Configuration

- **Name:** `kbd`
- **Group:** Inline
- **Inline:** The extension is applied as an inline node.
- **Atom:** The node behaves atomically.
- **Parse HTML:** Recognizes `<kbd>` tags when parsing HTML input.
- **Render HTML:** Outputs `<kbd>` tags with any additional HTML attributes.

## Customization

You can customize the `Kbd` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Kbd } from '@fusion/extension-kbd';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Kbd, /* other extensions */],
});
```

### HTML Output Example
```html
<p>Press <kbd>Ctrl</kbd> + <kbd>C</kbd> to copy text.</p>
```