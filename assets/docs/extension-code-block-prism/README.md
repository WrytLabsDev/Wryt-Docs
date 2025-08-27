# CodeBlockPrism Extension for Fusion Editor - @fusion/extension-code-block-prism

## Overview

The `CodeBlockPrism` extension allows you to highlight code blocks using the Prism syntax highlighter via the Refractor library. This extension is ideal for developers who need advanced syntax highlighting capabilities within the Fusion Editor.

## Features

- **Syntax Highlighting:** Highlights code blocks with support for a wide range of programming languages using Prism.
- **Customization:** Leverage the Refractor instance for custom language support and syntax highlighting customization.
- **ProseMirror Integration:** Fully integrated with the ProseMirror editor, allowing for seamless syntax highlighting in your code blocks.

## Commands

- **setCodeBlock:** Applies a code block to the selected text with optional language support.
    ```typescript
    editor.commands.setCodeBlock({ language: 'javascript' });
    ```

- **toggleCodeBlock:** Toggles the code block on or off with optional language support.
     ```typescript
    editor.commands.toggleCodeBlock({ language: 'javascript' });
    ```
## Configuration

### Default Configuration

- **Name:** codeBlockPrism
- **Language Class Prefix:** language- (applies language-specific classes to code blocks)
- **Default Language:** None (set a default language if required)
- **HTML Attributes:** Custom HTML attributes can be added to the <pre> tag.
- **Refractor Instance:** Pass a Refractor instance to support custom language configurations.

## Keyboard Shortcuts

- **Mod-Alt-c:** Toggles the code block on or off.

## Input Rules

- **Backtick Input Rule:** Automatically creates a code block when typing ````` followed by a space or newline.

- **Tilde Input Rule:** Automatically creates a code block when typing `~~~` followed by a space or newline.

## Usage Example
```typescript
import { CodeBlockPrism } from '@fusion/extension-code-block-prism';
import { refractor } from 'refractor';
import javascript from 'refractor/lang/javascript';

refractor.register(javascript);

const editor = new Editor({
  extensions: [
    CodeBlockPrism.configure({
      refractor,
      defaultLanguage: 'javascript',
    }),
    // other extensions
  ],
});

```

## HTML Output Example
```html
<pre class="language-javascript">
  <code class="language-javascript">
    console.log('Hello, world!');
  </code>
</pre>

```

