# Blockquote Extension for Fusion Editor - @fusion/extension-blockquote

## Overview

The `Blockquote` extension provides support for the `<blockquote>` element in Fusion Editor. Blockquotes are used to represent content that is quoted from another source, and this extension allows you to create, toggle, and manipulate blockquotes within your documents.

## Features

- **Blockquote Support:** Enables the use of `<blockquote>` elements to represent quoted content.
- **Customizable HTML Attributes:** Supports `cite` and other HTML attributes for blockquotes.
- **Keyboard Shortcuts:** Provides a default keyboard shortcut for quickly toggling blockquotes.
- **Input Rules:** Automatically formats text as a blockquote when a `>` character is used at the beginning of a line.

## Configuration

### Default Configuration

- **Name:** `blockquote`
- **Group:** `block` (Blockquotes are treated as block-level elements.)
- **Content:** `block+` (Allows block-level content inside the blockquote.)
- **Defining:** `true` (Defines a unique identity within the document.)
- **Parse HTML:** Recognizes the `<blockquote>` tag when parsing HTML input.
- **Render HTML:** Outputs a `<blockquote>` tag with any additional HTML attributes.
- **Priority:** `1000` (Ensures that the blockquote extension takes precedence in scenarios with potential conflicts.)

### Attributes

- **cite:** Specifies the source URL of the quote, typically included as a cite attribute.

### Keyboard Shortcuts

- **Mod-Shift-B:** Toggles the selected content as a blockquote.

### Input Rules
- **Blockquote Input Rule:** Automatically transforms text starting with `>` followed by a `space` into a blockquote.

### Commands
```typescript
// Example of setting a blockquote
editor.commands.setBlockquote();

// Example of toggling a blockquote
editor.commands.toggleBlockquote();

// Example of unsetting a blockquote
editor.commands.unsetBlockquote();

```

### Example

```typescript
import { Blockquote } from '@fusion/extension-blockquote';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Blockquote, /* other extensions */],
});
```

### HTML Output
```html

<blockquote cite="https://example.com">
  <p>Your quoted content here.</p>
</blockquote>

```
