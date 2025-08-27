# Menu Extension for Fusion Editor - @fusion/extension-menu

## Overview

The `Menu` extension allows you to insert `<menu>` elements within the Fusion Editor. The `<menu>` tag represents a group of commands or options and can be used to create toolbars, context menus, and more.

## Features

- **Block Node:** Renders the `<menu>` tag as a block-level node.
- **Command Integration:** Provides a command to insert menu elements with specified attributes like `type` and `label`.
- **HTML Attributes:** Supports attributes such as `type` (default: "list") and `label`.

## Attributes

- **type:** Specifies the type of the menu (`list`, `toolbar`, or `context`). Defaults to `list`.
- **label:** Provides a label for the menu (for accessibility purposes).

## Commands

- **insertMenu:** Inserts a `<menu>` element with the specified attributes and content.

## Configuration

### Default Configuration

- **Name:** `menu`
- **Block:** The extension is applied as a block node.
- **Parse HTML:** Recognizes the `<menu>` tag and its attributes when parsing HTML input.
- **Render HTML:** Outputs a `<menu>` tag with the provided attributes and content.

## Customization

You can customize the `Menu` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Menu } from '@fusion/extension-menu';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Menu, /* other extensions */],
});
```

## HTML Output Example
```html
<menu type="toolbar" label="Main Menu">...</menu>
```