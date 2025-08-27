# Select Extension for Fusion Editor - @fusion/extension-select

## Overview

The `Select` extension allows you to insert a `<select>` element within the Fusion Editor. This is useful for creating dropdown menus or multi-select options in your content.

## Features

- **Block Node:** Renders the `<select>` element as a block node to allow dropdown selections.
- **Command Integration:** Provides commands to insert a select element with customizable attributes.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<select>` element using the `HTMLAttributes` option.
- **name:** Specifies a name for the select element.
- **multiple:** Enables multiple selections if set to `true`.
- **required:** Marks the select element as required if set to `true`.

## Commands

- **setSelect:** Inserts a select element at the current cursor position.
```typescript
editor.commands.setSelect({ name: 'dropdown', multiple: false, required: true });
```

## Configuration
### Default Configuration
- **Name:** select
- **Block:** The extension is applied as a block node.
- **Parse HTML:** Recognizes <select> tags and their attributes when parsing HTML input.
- **Render HTML:** Outputs <select> tags with any additional HTML attributes.

## Usage Example
```typescript
import { Select } from '@fusion/extension-select';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Select, /* other extensions */],
});
```

## HTML Output Example
```html
  <label for="dropdown">Choose an option:</label>
  <select name="dropdown" required>
    <option value="1">Option 1</option>
    <option value="2">Option 2</option>
    <option value="3">Option 3</option>
  </select>
```