# Form Extension for Fusion Editor - @fusion/extension-form

## Overview

The `Form` extension allows users to insert and manage `<form>` elements in the Fusion Editor. Forms are crucial components of web development, enabling the collection of user input.

## Features

- **Customizable HTML Attributes:** Supports customization of HTML attributes for the form tag.
- **Block Content:** Allows block-level content, such as inputs, buttons, and other form controls, to be included within the form.
- **Defining Node:** Treats the form element as a defining node, making it a key structural element within the document.

## Configuration

### Default Configuration

The `Form` extension is customizable with the following default options:

- **Name:** `form`
- **Group:** `block` (Forms are treated as block-level elements.)
- **Content:** `block*` (Allows block-level elements such as inputs and buttons.)
- **HTML Attributes:** `{}` (Custom HTML attributes can be added to the form element.)
- **Defining:** `true` (Marks the form as a defining node.)

### Commands

- **insertForm:** Inserts a form element at the current selection.
  ```typescript
  editor.commands.insertForm();
  ```

## Usage
```typescript
const editor = new Editor({
  extensions: [
    Form.configure({
      HTMLAttributes: {
        action: '/submit',
        method: 'post',
      },
    }),
  ],
});
```

## HTML Output
```html
<form action="/submit" method="post">
  <!-- Block-level content goes here -->
</form>
```