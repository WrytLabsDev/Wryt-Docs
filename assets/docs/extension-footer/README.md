# Footer Extension for Fusion Editor - @fusion/extension-footer

## Overview

The `Footer` extension allows users to insert and manage `<footer>` elements in the Fusion Editor. A footer is typically used to contain metadata or navigational links at the bottom of a document or section.

## Features

- **Customizable HTML Attributes:** Supports customization of HTML attributes for the `<footer>` tag.
- **Block Content:** Allows block-level content such as paragraphs, navigation links, and other metadata.
- **Defining Node:** Marks the footer as a defining node, making it a key structural element in the document.

## Configuration

### Default Configuration

The `Footer` extension is customizable with the following default options:

- **Name:** `footer`
- **Group:** `block` (The footer is treated as a block-level element.)
- **Content:** `block*` (Allows block-level elements such as paragraphs and links.)
- **HTML Attributes:** `{}` (Custom HTML attributes can be added to the footer.)
- **Defining:** `true` (Marks the footer as a defining node.)

### Commands

- **insertFooter:** Inserts a footer element at the current selection.
  ```typescript
  editor.commands.insertFooter();
  ```

## Usage
```typescript
  const editor = new Editor({
  extensions: [
    Footer.configure({
      HTMLAttributes: {
        class: 'page-footer',
        role: 'contentinfo',
      },
    }),
  ],
});
```

## HTML Output
```html
<footer class="page-footer" role="contentinfo">
  <!-- Block-level content goes here -->
</footer>
```
