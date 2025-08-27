# Code Block Extension for Fusion Editor - @fusion/extension-code-block

## Overview

The `CodeBlock` extension allows you to create and manage code blocks within the Fusion Editor. This extension is ideal for displaying code snippets with syntax highlighting and supports multiple programming languages.

## Features

- **Block Node:** Renders the `<pre><code>` block-level element for displaying code.
- **Language Support:** Supports specifying the programming language for syntax highlighting.
- **Keyboard Shortcuts:** Easily toggle code blocks using keyboard shortcuts.
- **Input Rules:** Automatically create code blocks using backticks (```) or tildes (~~~).
- **Triple Enter Exit:** Allows exiting the code block with triple Enter key press.
- **Arrow Down Exit:** Exits the code block when pressing Arrow Down at the end of the block.
- **VS Code Paste Integration:** Automatically detects language from code pasted from VS Code.

## Attributes

- **language:** Specifies the programming language for syntax highlighting. If no language is provided, the default language or no language will be used.
- **HTML Attributes:** Customize the HTML attributes of the `<pre><code>` element using the `HTMLAttributes` option.

## Commands

- **setCodeBlock:** Inserts a code block with optional language attribute.
  ```typescript
  editor.commands.setCodeBlock({ language: 'javascript' });
  ```

- **toggleCodeBlock:** Toggles the code block on or off.
  ```typescript
  editor.commands.toggleCodeBlock({ language: 'javascript' });

  ```

## Configuration

### Default Configuration

- **Name:** codeBlock
- **Block:** The extension is applied as a block node.
- **Code:** The node is treated as a code block.
- **Parse HTML:** Recognizes `<pre><code>` tags when parsing HTML input.
- **Render HTML:** Outputs `<pre><code>` tags with any additional HTML attributes.
- **Default Language:** No default language is set unless specified.
- **Exit on Triple Enter:** Allows exiting the code block with a triple Enter key press.
- **Exit on Arrow Down:** Exits the code block when pressing Arrow Down at the end of the block.

## Keyboard Shortcuts

- **Mod-Alt-c:** Toggles the code block on or off.

## Input Rules

- **Backtick Input Rule:** Automatically creates a code block when typing ````` followed by a space or newline.

- **Tilde Input Rule:** Automatically creates a code block when typing `~~~` followed by a space or newline.

## VS Code Paste Integration

- **Automatic Language Detection:** Detects the language when pasting code from VS Code and applies the appropriate language class.

## Usage Example

```typescript
import { CodeBlock } from '@fusion/extension-code-block';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [CodeBlock, /* other extensions */],
});

```

## HTML Output Example
```html
<pre><code class="language-javascript">console.log('Hello, world!');</code></pre>
```