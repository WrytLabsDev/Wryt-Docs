# Case Extension - @fusion/extension-case

The `Case` extension adds text case transformation capabilities to your editor, allowing users to change the case of selected text with five different transformation options. This extension provides functionality similar to Microsoft Word's case transformation features.

## Overview

This extension enables case transformations on selected text within the editor. It supports five different case modes that can be applied through editor commands. The transformations preserve all text formatting and document structure while maintaining the original selection after transformation.

## Features

- **Sentence Case**: Capitalizes the first letter of each sentence
- **Lowercase**: Converts all text to lowercase
- **Uppercase**: Converts all text to uppercase
- **Capitalize Each Word**: Capitalizes the first letter of every word
- **Toggle Case**: Inverts the case of each character
- Preserves text formatting (bold, italic, etc.)
- Maintains original selection after transformation
- Full TypeScript support with strict typing

## Commands

| Command   | Parameters        | Description |
| --------- | ----------------- | ----------- |
| `setCase` | `type: 'sentence' | 'lower'     | 'upper' | 'capitalize' | 'toggle'` | Applies the specified case transformation to selected text |

## Installation

To use the `Case` extension, import it into your editor configuration:

```typescript
import { FontCase } from '@fusion/extension-font';
```

## Usage

### Basic Setup

Add the Case extension to your editor's extensions:

```typescript
import { Editor } from '@tiptap/core';
import StarterKit from '@tiptap/starter-kit';
import { FontCase } from '@fusion/extension-font';

const editor = new Editor({
  extensions: [
    StarterKit,
    FontCase,
    // other extensions
  ],
});
```

## Applying Case Transformations

Use the `setCase` command to transform selected text:

```typescript
// Apply sentence case to selected text
editor.commands.setCase('sentence');

// Convert selection to lowercase
editor.commands.setCase('lower');

// Convert selection to uppercase
editor.commands.setCase('upper');

// Capitalize each word in selection
editor.commands.setCase('capitalize');

// Toggle case of each character
editor.commands.setCase('toggle');
```

## UI Implementation Example

Create toolbar buttons to trigger case transformations:

```typescript
<div class="toolbar">
  <button onclick="editor.commands.setCase('sentence')">Sentence Case</button>
  <button onclick="editor.commands.setCase('lower')">lowercase</button>
  <button onclick="editor.commands.setCase('upper')">UPPERCASE</button>
  <button onclick="editor.commands.setCase('capitalize')">Title Case</button>
  <button onclick="editor.commands.setCase('toggle')">tOGGLE cASE</button>
</div>
```

## Transformation Details

- **Sentence Case**: Capitalizes first letter after sentence-ending punctuation (., !, ?)

- **Capitalize Each Word**: Capitalizes first letter of words using word boundaries

- **Toggle Case**: Inverts case only for alphabetic characters

All transformations preserve non-alphabetic characters and formatting

Only modifies selected text (does nothing if no text is selected)

