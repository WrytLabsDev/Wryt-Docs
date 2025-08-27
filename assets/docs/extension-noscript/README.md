# `<noscript>` Extension for Fusion Editor - @fusion/extension-noscript

## Overview

The `<noscript>` extension allows you to include content that will be displayed when JavaScript is disabled in the user's browser. This extension is useful for providing alternative content or instructions to users who have JavaScript turned off.

## Features

- **JavaScript Fallback:** Displays content when JavaScript is disabled.
- **Versatile Content:** Supports any HTML content within the `<noscript>` tag.
- **Customizable Display:** Customize the fallback content as needed.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<noscript>` element using the `HTMLAttributes` option.

## Commands

- **insertNoscript:** Inserts a `<noscript>` element into the document.

## Configuration

### Default Configuration

- **Name:** `noscript`
- **Group:** The extension is applied as a block-level element.
- **Parse HTML:** Recognizes `<noscript>` tags when parsing HTML input.
- **Render HTML:** Outputs `<noscript>` tags with any additional HTML attributes.

## Keyboard Shortcuts

- **None:** Currently, no default keyboard shortcuts are defined for this extension.

## Customization

You can customize the `<noscript>` extension by passing in content through the `content` option in the `insertNoscript` command.

## Usage Example

```typescript
import { NoscriptExtension } from '@fusion/extension-noscript';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [NoscriptExtension, /* other extensions */],
});

// Insert a <noscript> element
editor.commands.insertNoscript({
  content: [
    { type: 'paragraph', content: [{ type: 'text', text: 'JavaScript is disabled. Please enable JavaScript for a better experience.' }] }
  ]
});
```

## HTML Output Example

When rendered, the <noscript> tag will display as follows if JavaScript is disabled:

```typescript
<noscript>
  <p>JavaScript is disabled. Please enable JavaScript to view this content.</p>
</noscript>

```