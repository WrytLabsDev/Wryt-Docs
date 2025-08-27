# CodeBlockLowlight Extension for Fusion Editor - @fusion/extension-code-block-lowlight

## Overview

The `CodeBlockLowlight` extension enhances the basic `CodeBlock` extension by adding syntax highlighting using the Lowlight library. This extension is useful for displaying code snippets with syntax highlighting in the Fusion Editor.

## Features

- **Syntax Highlighting:** Automatically highlights code blocks using Lowlight.
- **Customizable Language Support:** Supports a wide range of programming languages through Lowlight.
- **Command Integration:** Provides commands to set and toggle code blocks with optional language-specific highlighting.
- **Keyboard Shortcuts:** Easily create and toggle code blocks using keyboard shortcuts.
- **Input Rules:** Automatically create code blocks when typing specific markdown-like syntax.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<pre>` element using the `HTMLAttributes` option.
- **Language:** Specify the language for syntax highlighting.

## Commands

- **setCodeBlock:** Applies a code block to the selected text with optional language highlighting.
  ```typescript
  editor.commands.setCodeBlock({ language: 'javascript' });
  ```

- **toggleCodeBlock:** Toggles the code block on or off, with optional language highlighting.
  ```typescript
    editor.commands.toggleCodeBlock({ language: 'javascript' });
  ```

## Configuration

### Default Configuration

- **Name:** codeBlockLowlight
- **Lowlight Instance:** Pass your configured Lowlight instance to the extension.
- **Language Class Prefix:** The prefix added to language classes (default: language-).
- **Exit on Triple Enter:** Exits the code block when pressing Enter three times.
- **Exit on Arrow Down:** Exits the code block when pressing Arrow Down at the end of the block.
- **Default Language:** The default language for code blocks (optional).

## Keyboard Shortcuts

- **Mod-Alt-c:** Toggles the code block on or off.

## Input Rules

- **Backtick Input Rule:** Automatically creates a code block when typing ````` followed by a space or newline.

- **Tilde Input Rule:** Automatically creates a code block when typing `~~~` followed by a space or newline.

## Usage Example

```typescript
import { CodeBlockLowlight } from '@fusion/extension-code-block-lowlight';
import lowlight from 'lowlight/lib/core';
import javascript from 'highlight.js/lib/languages/javascript';

lowlight.registerLanguage('javascript', javascript);

const editor = new Editor({
  extensions: [
    CodeBlockLowlight.configure({
      lowlight,
      defaultLanguage: 'javascript',
    }),
    // other extensions...
  ],
});
```

## HTML Output Example

```html
<pre><code class="language-javascript">console.log('Hello, world!');</code></pre>
```
