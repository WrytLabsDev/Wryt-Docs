# Data Extension for Fusion Editor - @fusion/extension-data

## Overview

The `Data` extension enables support for the `<data>` HTML element within the Fusion Editor. This element is designed to link visible content with machine-readable data, making it useful for scenarios where structured data needs to be embedded within text content.

## Features

- **Inline Element**: The `<data>` element is treated as an inline element, allowing it to be embedded seamlessly within text.
- **Customizable Attributes**: You can set and customize attributes such as `value` to store machine-readable data.
- **Commands**:
  - `setData`: Inserts a new `<data>` element with specified attributes.
  - `unsetData`: Removes the `<data>` element and converts it to plain text.

### Commands

- **setData:** Inserts a <data> element with the specified attributes.
```typescript
editor.commands.setData({
  value: 'machine-readable-value',
  'data-custom': 'custom-attribute',
});
```
- **unsetData:** Removes the <data> element, converting it back to plain text.
```typescript
editor.commands.unsetData();
```

## Example Usage

```typescript
import { Data } from './path/to/your/data-extension';

const editor = new Editor({
  extensions: [
    Data,
    // other extensions
  ],
});
```

### HTML Output

```html
<data value="12345" data-info="example-data">Visible Content</data>
```