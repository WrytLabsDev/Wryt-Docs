# `<figure>` and `<figcaption>` Extension

## Overview

This extension allows you to add `<figure>` and `<figcaption>` elements to your editor. These are typically used to display media (such as images) with an associated caption.

- `<figure>`: Used to group media content.
- `<figcaption>`: Provides a caption for the content inside the `<figure>`.

## Features

- Nest media and other content inside `<figure>`.
- Automatically associate a `<figcaption>` with its parent `<figure>`.
- Ensure accessibility by using the first `<figcaption>` as the figure's accessible name.

## Attributes

### `<figure>` attributes:
- **class**: Adds a CSS class to the figure.
- **id**: Adds an ID to the figure.

### `<figcaption>` attributes:
- **class**: Adds a CSS class to the figcaption.
- **id**: Adds an ID to the figcaption.

## Commands

### Insert Figure
```typescript
editor.commands.insertFigure({ class: 'my-figure', id: 'figure-1' });
```

#### Insert Figcaption

```typescript
editor.commands.insertFigcaption({ class: 'my-caption', id: 'caption-1' });
```

## Usage Example

```typescript
const editor = new Editor({
  extensions: [
    Figure,
    Figcaption
  ],
});

editor.chain().focus().insertFigure({ class: 'custom-figure' }).run();

```

## HTML Output Example

```html
<figure class="custom-figure">
  <figcaption>Caption here</figcaption>
  <img src="example.jpg" alt="Example Image">
</figure>
```

### Key Notes:
- The `<figure>` element groups together media content.
- The `<figcaption>` must be the first or last child inside the `<figure>`.
- For accessibility, the first `<figcaption>` is treated as the figure’s caption.
