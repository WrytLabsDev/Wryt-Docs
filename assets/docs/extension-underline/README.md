# Underline Extension for Fusion Editor - @fusion/extension-underline

## Overview

The `Underline` extension allows you to underline text within the Fusion Editor. This extension is useful for emphasizing important content or creating stylistic effects in your text.

## Features

- **Inline Mark:** Renders the `<u>` element as an inline mark to underline text.
- **Command Integration:** Provides commands to set, toggle, and unset underline marks.
- **Keyboard Shortcuts:** Easily underline text using keyboard shortcuts.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<u>` element using the `HTMLAttributes` option.

## Commands

- **setUnderline:** Applies the underline mark to selected text.
- **toggleUnderline:** Toggles the underline mark on or off.
- **unsetUnderline:** Removes the underline mark from selected text.

## Configuration

### Default Configuration

- **Name:** `underline`
- **Inline:** The extension is applied as an inline mark.
- **Parse HTML:** Recognizes `<u>` tags and `text-decoration: underline;` style when parsing HTML input.
- **Render HTML:** Outputs `<u>` tags with any additional HTML attributes.

## Keyboard Shortcuts

- **Mod-u:** Toggles the underline mark on or off.
- **Mod-U:** (Alternate shortcut) Toggles the underline mark on or off.

## Customization

You can customize the `Underline` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Underline } from '@fusion/extension-underline';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Underline, /* other extensions */],
});
```

## HTML Output Example

```html
<p>This text is <u>underlined</u>.</p>
```

