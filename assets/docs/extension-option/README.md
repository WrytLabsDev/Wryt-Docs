# Option Extension for Fusion Editor - @fusion/extension-option

## Overview

The `Option` extension allows you to create `<option>` elements within the Fusion Editor. The `<option>` element is typically used within a `<select>` dropdown menu, providing users with selectable options.

## Features

- **Selectable Options:** Create options within a dropdown menu.
- **Customizable Attributes:** Supports common attributes like `value`, `selected`, `disabled`, and `label`.
- **Inline Content:** Designed to be used within inline groups. Renders the `<option>` element as an inline node.

## Commands

- **setOption:** Adds an option element to the editor with the specified attributes.
    ```typescript
    editor.commands.setOption({
    value: '1',
    selected: true,
    disabled: false,
    label: 'Option 1',
    });
    ```
- **unsetOption:** Removes the option node.
    ```typescript
    editor.commands.unsetOption();
    ```
## Configuration

### Default Configuration

- **Name:** `option`
- **Group:** `inline`
- **Content:** `text*` (Allows text content inside the option.)
- **Parse HTML:** Recognizes `<option>` tags when parsing HTML input.
- **Render HTML:** Outputs `<option>` tags with any additional HTML attributes.

## Customization

You can customize the `Option` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Option } from '@fusion/extension-option';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Option, /* other extensions */],
});
```

## HTML Output

- This `Option` extension supports creating and manipulating `<option>` elements in the editor, providing flexibility for managing dropdown options or select inputs within your content.

```html
<option value="1">Option 1</option>
```
