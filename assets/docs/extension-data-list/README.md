# Datalist Extension for Fusion Editor - @fusion/extension-data-list

## Overview

The `Datalist` extension provides support for the `<datalist>` HTML element in the Fusion Editor. The `<datalist>` element is used to provide an "autocomplete" feature for `<input>` elements, enabling users to select from pre-defined options.

## Features

- **Block-Level Element**: The `<datalist>` element is treated as a block-level element.
- **Supports Child Elements**: Only `<option>` elements are allowed inside a `<datalist>`.
- **Customizable Attributes**: You can set attributes like `id` to associate the `<datalist>` with an `<input>` element.
- **Commands**:
  - `setDatalist`: Inserts a new `<datalist>` element with specified attributes.
  - `toggleDatalist`: Toggles the presence of a `<datalist>` element.
  - `unsetDatalist`: Removes the `<datalist>` element and converts it to a paragraph.

## Commands

- setDatalist: Inserts a `<datalist>` element with optional attributes.
    ```typescript
        editor.commands.setDatalist({
        id: 'example-datalist', // optional
        });
    ```
- toggleDatalist: Toggles the presence of a `<datalist>` element.
    ```typescript
        editor.commands.toggleDatalist({
            id: 'example-datalist',
        });
    ```
- unsetDatalist: Removes the `<datalist>` element, converting it to a paragraph.
    ```typescript
        editor.commands.unsetDatalist();
    ```

### Usage Example

To install the extension, include it in your editor setup as shown below:

```typescript
import { Datalist } from './path/to/your/datalist-extension';

const editor = new Editor({
  extensions: [
    Datalist,
    // other extensions
  ],
});
```

### HTML Output Example

```html
<datalist id="ice-cream-flavors">
  <option value="Chocolate"></option>
  <option value="Coconut"></option>
  <option value="Mint"></option>
  <option value="Strawberry"></option>
  <option value="Vanilla"></option>
</datalist>
```