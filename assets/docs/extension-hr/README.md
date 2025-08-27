# Horizontal Rule Extension

## Overview

The **Horizontal Rule** extension allows you to insert a horizontal rule (`<hr>`) into your Tiptap editor. This node is a block-level element that separates content sections with a horizontal line.

## Features

- Insert a horizontal rule (`<hr>`) into the editor.
- Customizable via HTML attributes.
- Includes input rules for inserting the horizontal rule by typing `---`, `___`, or `***`.

## Attributes

| Attribute   | Description                   | Default |
| ----------- | ----------------------------- | ------- |
| `class`     | CSS class for the `<hr>`       | `null`  |

## Commands

### `setHorizontalRule`

Inserts a horizontal rule into the editor at the current selection.

#### Usage

```typescript
editor.commands.setHorizontalRule();
```

## Input Rules

You can insert a horizontal rule by typing any of the following patterns:

- `---`
- ___
- ***
These input rules will automatically convert the typed characters into a horizontal rule.

## Usage Example

```typescript
const editor = new Editor({
  extensions: [
    HorizontalRule.configure({
      HTMLAttributes: {
        class: 'horizontal-line',
      },
    }),
    /* Other extensions */
  ],
});
```

## HTML Output

```html
<hr class="custom-hr" />
```
