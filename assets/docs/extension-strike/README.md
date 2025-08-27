# Strike Extension for Fusion Editor - @fusion/extension-strike

## Overview

The `Strike` extension allows you to apply strikethrough formatting to text within the Fusion Editor. This is particularly useful for marking text as obsolete or deleted.

## Features

- **Inline Mark:** Renders the `<s>`, `<del>`, or `<strike>` elements as an inline mark to strike through text.
- **Command Integration:** Provides commands to set, toggle, and unset strikethrough marks.
- **Keyboard Shortcuts:** Easily apply strikethrough using keyboard shortcuts.
- **Input & Paste Rules:** Automatically applies strikethrough formatting when using specific markdown syntax (`~~strike~~`).

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<s>` element using the `HTMLAttributes` option.

## Commands

- **setStrike:** Applies the strikethrough mark to selected text.
```typescript
editor.commands.setStrike();
```
- **toggleStrike:** Toggles the strikethrough mark on or off.
```typescript
editor.commands.toggleStrike();
```
- **unsetStrike:** Removes the strikethrough mark from selected text.
```typescript
editor.commands.unsetStrike();
```

## Configuration

### Default Configuration

- **Name:** `strike`
- **Inline:** The extension is applied as an inline mark.
- **Parse HTML:** Recognizes `<s>`, `<del>`, `<strike>` tags, and `text-decoration: line-through;` style when parsing HTML input.
- **Render HTML:** Outputs `<s>` tags with any additional HTML attributes.

## Keyboard Shortcuts

- **Mod-Shift-s:** Toggles the strikethrough mark on or off.

## Input Rules

- **Markdown Syntax:** Automatically applies the strikethrough mark when typing `~~strike~~`.

## Paste Rules

- **Markdown Syntax:** Automatically applies the strikethrough mark when pasting `~~strike~~` text.

## Customization

You can customize the `Strike` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Strike } from '@fusion/extension-strike';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Strike, /* other extensions */],
});
```

## HTML Output Example

```html
<p>This text is <s>struck through</s>.</p>
```