# Clipboard Extension - @fusion/extension-clipboard

The `Clipboard` extension adds support for enhanced clipboard operations in your Fusion Editor, including `copy`, `cut`, and `paste`. When no text is selected, the extension copies or cuts the entire parent block node (e.g., paragraph, heading, image, etc.), improving editing efficiency.

## Overview

This extension enhances the native clipboard behavior by allowing copy and cut of the entire block if no selection is made. It also supports pasting plain text from the system clipboard using the Clipboard API.

## Features

- Copies the selected text or the full block if no selection is made.
- Cuts the selected text or the full block if no selection is made.
- Pastes plain text from the clipboard at the current cursor position.
- Fully supports keyboard shortcuts: `Ctrl/Cmd+C`, `Ctrl/Cmd+X`, and `Ctrl/Cmd+V`.

## Commands

| Command   | Parameters | Description                                                           |
| --------- | ---------- | --------------------------------------------------------------------- |
| `copy()`  | –          | Copies selected content, or the entire block if no selection is made. |
| `cut()`   | –          | Cuts selected content, or the entire block if no selection is made.   |
| `paste()` | –          | Pastes content from the clipboard at the current cursor position.     |

### Example Command Usage

```typescript
editor.commands.copy();
editor.commands.cut();
editor.commands.paste();
```

## Installation
- To use the Clipboard extension, import and include it in your Tiptap editor setup:

`import { Clipboard } from '@fusion/extension-clipboard';`


## Usage

- Add the extension to the editor configuration:

```typescript
import { Editor } from '@tiptap/core';
import { Clipboard } from '@fusion/extension-clipboard';

const editor = new Editor({
  extensions: [
    Clipboard,
    // ...other extensions
  ],
});
```

## Keyboard Shortcuts

| Shortcut       | Action |
| -------------- | ------ |
| `Ctrl/Cmd + C` | Copy   |
| `Ctrl/Cmd + X` | Cut    |
| `Ctrl/Cmd + V` | Paste  |



