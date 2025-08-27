# Highlight Extension for Fusion Editor - @fusion/extension-highlight

## Overview
The Highlight extension allows you to apply highlight formatting to text within the Fusion Editor. It supports customizable highlight colors and provides input and paste rules for markdown-like syntax.

## Features
- **Highlight Support:** Enables text highlighting using the `<mark>` element.
- **Multicolor Support:** Allows multiple highlight colors when enabled.
- **Markdown-like Syntax:** Supports `==highlight==` for input and paste highlighting.
- **Customizable HTML Attributes:** Allows adding custom HTML attributes to highlighted text.
- **Keyboard Shortcuts:** Provides shortcuts for applying highlights quickly.

## Configuration
#### Default Configuration
- **Name:** `highlight`
- **Multicolor:** `false` (Set to `true` to enable custom colors)
- **HTML Attributes:** `{}` (Additional HTML attributes can be applied)

## Keyboard Shortcuts
- **Mod-Shift-H:** Toggles highlight formatting for the selected text.

## Input Rules
- `==highlight==`: Wraps the selected text in `==` to apply a highlight.

## Paste Rules
- `==highlight==`: Automatically converts `==highlight==` into highlighted text when pasted.

## Commands
- **setHighlight:** Applies a highlight to the selected text.
  ```typescript
  editor.commands.setHighlight({ color: 'yellow' });
  ```

- **toggleHighlight:** Toggles highlight formatting on or off.
  ```typescript
  editor.commands.toggleHighlight({ color: 'blue' });
  ```

- **unsetHighlight:** Removes the highlight formatting from the selected text.
  ```typescript
  editor.commands.unsetHighlight();
  ```

## Example
```typescript
import { Highlight } from '@fusion/extension-highlight';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Highlight.configure({
    multicolor: true,
    HTMLAttributes: { class: 'custom-highlight' },
  })],
});
```

## HTML Output Example
```html
<mark data-color="yellow" style="background-color: yellow; color: inherit">Highlighted Text</mark>
```

