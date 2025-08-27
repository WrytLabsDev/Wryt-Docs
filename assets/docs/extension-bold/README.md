# Bold Extension for Fusion Editor - @fusion/extension-bold

## Overview
The Bold extension enables bold text formatting in the Fusion Editor. This extension provides support for bold text using various HTML tags and styles, and includes input and paste rules for markdown-like syntax.

## Features
- **Bold Text Support:** Enables the use of <strong> and <b> elements for bold text.
- **Markdown-like Syntax:** Supports **bold** and __bold__ syntax for easy input and pasting.
- **Customizable HTML Attributes:** Allows customization of HTML attributes for bold elements.
- **Keyboard Shortcuts:** Provides default keyboard shortcuts for toggling bold formatting.

## Configuration
#### Default Configuration

- Name: bold
- Group: inline
- Parse HTML: Recognizes <strong>, <b>, and styles with font-weight as bold text.
- Render HTML: Outputs <strong> tags with any additional HTML attributes.
- Priority: 1000 (Ensures that the bold extension takes precedence in scenarios with potential conflicts.)

## Keyboard Shortcuts
- Mod-b / Mod-B: Toggles bold formatting for the selected text.

## Input Rules
- `**bold**`: Wraps the selected text in ** to make it bold.
- `__bold__`: Wraps the selected text in __ to make it bold.

## Paste Rules
- `**bold**`: Automatically converts `**bold**` into bold text when pasted.
- `__bold__`: Automatically converts `__bold__` into bold text when pasted.

## Commands
- **setBold:** Applies bold formatting to the selected text.
- **toggleBold:** Toggles bold formatting on or off for the selected text.
- **unsetBold:** Removes bold formatting from the selected text.

## Example
```typescript
import { Bold } from '@fusion/extension-bold';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Bold, /* other extensions */],
});
```

## HTML Output

```html
<strong>bold text</strong>
```
