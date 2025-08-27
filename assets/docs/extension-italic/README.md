# Italic Extension for Fusion Editor - @fusion/extension-italic

## Overview

The `Italic` extension allows you to italicize text within the Fusion Editor. This extension is useful for emphasizing text and providing stylistic variety in your content.

## Features

- **Inline Mark:** Renders the `<em>` or `<i>` elements as an inline mark to italicize text.
- **Command Integration:** Provides commands to set, toggle, and unset italic marks.
- **Keyboard Shortcuts:** Easily italicize text using keyboard shortcuts.
- **Input & Paste Rules:** Automatically applies italic formatting when using specific markdown syntax (`*italic*` or `_italic_`).

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<em>` element using the `HTMLAttributes` option.

## Commands

- **setItalic:** Applies the italic mark to selected text.
- **toggleItalic:** Toggles the italic mark on or off.
- **unsetItalic:** Removes the italic mark from selected text.

## Configuration

### Default Configuration

- **Name:** `italic`
- **Inline:** The extension is applied as an inline mark.
- **Parse HTML:** Recognizes `<em>` and `<i>` tags and `font-style: italic;` style when parsing HTML input.
- **Render HTML:** Outputs `<em>` tags with any additional HTML attributes.

## Keyboard Shortcuts

- **Mod-i:** Toggles the italic mark on or off.
- **Mod-I:** (Alternate shortcut) Toggles the italic mark on or off.

## Customization

You can customize the `Italic` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Italic } from '@fusion/extension-italic';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Italic, /* other extensions */],
});
```

## HTML Output Example

```html
<p>This text is <em>italicized</em>.</p>
```