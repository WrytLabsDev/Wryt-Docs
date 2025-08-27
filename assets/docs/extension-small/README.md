# Small Extension for Fusion Editor - @fusion/extension-small

## Overview

The `Small` extension allows you to format text as smaller than the surrounding text within the Fusion Editor. This extension is useful for making text appear less prominent.

## Features

- **Inline Mark:** Renders the `<small>` element as an inline mark to reduce the font size of text.
- **Command Integration:** Provides commands to set, toggle, and unset small marks.
- **Keyboard Shortcuts:** Easily apply the small format using keyboard shortcuts.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<small>` element using the `HTMLAttributes` option.

## Commands

- **setSmall:** Applies the small mark to selected text.
```typescript
editor.commands.setSmall();
```

- **toggleSmall:** Toggles the small mark on or off.
```typescript
editor.commands.toggleSmall();
```

- **unsetSmall:** Removes the small mark from selected text.
```typescript
editor.commands.unsetSmall();
```

## Configuration

### Default Configuration
- **Name:** small
- **Inline:** The extension is applied as an inline mark.
- **Parse HTML:** Recognizes <small> tags and font-size: small; style when parsing HTML input.
- **Render HTML:** Outputs <small> tags with any additional HTML attributes.

## Usage Example

```typescript
import { Small } from '@fusion/extension-small';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Small, /* other extensions */],
});
```

## HTML Output Example
```html
<p><small>The content is licensed under a Creative Commons Attribution-ShareAlike 2.5 Generic License.</small></p>
```
