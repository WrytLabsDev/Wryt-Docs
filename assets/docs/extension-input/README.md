# Input Extension for Fusion Editor - @fusion/extension-input

## Overview

This extension allows the creation of the HTML `<input>` tag in both block and inline formats using Tiptap.

- The block-level `input` tag is used as a form input control, which can accept different types of input like `text`, `password`, `email`, etc.
- The inline-level `input` tag is similar but allows insertion within inline contexts.

## Features

- Supports `type`, `value`, `class`, `id`, and `disabled` attributes.
- Can insert both block-level and inline-level input fields.

## Attributes

- `type`: Specifies the type of input control (default: `"text"`).
- `value`: Defines the default value of the input element.
- `class`: Assigns one or more class names for CSS.
- `id`: Provides a unique identifier for the input element.
- `disabled`: Specifies whether the input is disabled.

## Commands

### Block-level Input

```typescript
editor.commands.insertInput({
  attrs: { type: 'text', value: 'default', class: 'input-class' },
});
```

### Inline-level Input

```typescript
editor.commands.insertInlineInput({
  attrs: { type: 'text', value: 'default', class: 'input-class' },
});
```

## Usage Example
```typescript
import { Input } from '@fusion/extension-input';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Input
    InlineInput,
    /* other extensions */
  ],
});
```

## HTML Output Example
```html
<input type="text" value="default" class="input-class" />

<p>Here is input inside p tag: <input type="text" value="inline" class="inline-input" /><p>
```