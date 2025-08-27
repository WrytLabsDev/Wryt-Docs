# WBR Extension for Fusion Editor - @fusion/extension-wbr

## Overview

The `WBR` extension allows you to insert `<wbr>` elements, which represent a word break opportunity. This is useful for managing word wrapping in long text sequences within the Fusion Editor.

## Features

- **Inline Support:** Renders the `<wbr>` element as an inline node.
- **Command Integration:** Provides a command to insert a word break opportunity at the desired location.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<wbr>` element.

## Commands

- **setWBR:** Inserts a `<wbr>` node.

## Configuration

### Default Configuration

- **Name:** `wbr`
- **Group:** `inline`
- **Selectable:** `false` (The element is not selectable.)
- **Atom:** `true` (The element behaves as a single unit.)
- **Parse HTML:** Recognizes `<wbr>` tags when parsing HTML input.
- **Render HTML:** Outputs `<wbr>` tags with any additional HTML attributes.

## Keyboard Shortcuts

Currently, there are no keyboard shortcuts provided by default for the `WBR` extension.

## Customization

You can customize the `WBR` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { WBR } from '@fusion/extension-wbr';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [WBR, /* other extensions */],
});
```

## HTML Output Example

```html
<p>
  http://this<wbr />.is<wbr />.a<wbr />.really<wbr />.long<wbr />.example<wbr />.com/With<wbr />/deeper<wbr />/level<wbr />/pages<wbr />/deeper<wbr />/level<wbr />/pages<wbr />/deeper<wbr />/level<wbr />/pages<wbr />/deeper<wbr />/level<wbr />/pages<wbr />/deeper<wbr />/level<wbr />/pages
</p>
```
