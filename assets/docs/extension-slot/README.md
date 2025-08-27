# Slot Extension for Fusion Editor - @fusion/extension-slot

## Overview

The `Slot` extension allows you to insert a `<slot>` element within the Fusion Editor. This is particularly useful when working with web components, enabling content projection.

## Features

- **Inline Node:** Renders the `<slot>` element as an inline node.
- **Command Integration:** Provides commands to insert a slot element with optional attributes.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<slot>` element using the `HTMLAttributes` option.
- **name:** Specifies a name for the slot, enabling named slots in web components.

## Commands

- **setSlot:** Inserts a slot element at the current cursor position.
```typescript
editor.commands.setSlot({ name: 'default' });
```

## Configuration
### Default Configuration
- **Name:** slot
- **Inline:** The extension is applied as an inline node.
- **Parse HTML:** Recognizes <slot> tags and their attributes when parsing HTML input.
- **Render HTML:** Outputs <slot> tags with any additional HTML attributes.

## Usage Example

```typescript
import { Slot } from '@fusion/extension-slot';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Slot, /* other extensions */],
});
```

HTML Output Example
```html
<p>This is a <slot name="default"></slot> slot element.</p>
```
