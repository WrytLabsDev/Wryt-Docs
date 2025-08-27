# Dialog Extension for Fusion Editor - @fusion/extension-dialog

## Overview

The `Dialog` extension provides support for the `<dialog>` HTML element in Fusion Editor. This extension allows you to create and manage modal dialogs, which are useful for interactive content such as forms or messages that require user interaction.

## Features

- **Modal Dialog Support:** Easily create and manage `<dialog>` elements with customizable content.
- **Customizable HTML Attributes:** Supports `open` and `id` attributes, with the ability to add custom attributes.
- **Draggable and Selectable:** Dialog elements can be dragged and selected for easy manipulation.

## Configuration

### Default Configuration

The `Dialog` extension is flexible with the following defaults:

- **Name:** `dialog`
- **Group:** `block` (Dialog elements are treated as block-level nodes.)
- **Content:** `block*` (Allows block-level content within dialogs.)
- **HTML Attributes:** `{}` (Custom HTML attributes for the dialog.)
- **Defining:** `true` (Indicates that the node is defining.)
- **Draggable:** `true` (Dialog nodes are draggable.)

### Commands

- **insertDialog:** Inserts a dialog element with specified attributes and content.
  ```typescript
  editor.commands.insertDialog({
    attrs: { open: true, id: 'dialog-id' },
    content: [{ type: 'paragraph', content: [{ type: 'text', text: 'This is a dialog' }] }]
  });
  ```

## Usage
```typescript
const editor = new Editor({
  extensions: [
    Dialog.configure({
      HTMLAttributes: { open: true, id: 'example-dialog' },
    }),
  ],
});
```

## HTML Output
```html
<dialog open id="example-dialog">
  <p>This is a dialog</p>
</dialog>
```