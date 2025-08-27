# Textarea Extension for Fusion Editor - @fusion/extension-textarea

## Overview

The `Textarea` extension for Fusion Editor allows you to use `<textarea>` elements within your editor. This extension supports block content and provides attributes for handling text input fields.

## Features

- **Block Content**: The `<textarea>` element is treated as a block element.
- **Attributes**: Adds support for `name`, `rows`, `cols`, `placeholder`, and `required` attributes.

## Attributes

- **name**: The name of the `<textarea>` element.
- **rows**: The number of visible text lines.
- **cols**: The number of visible text columns.
- **placeholder**: A short hint displayed in the `<textarea>` when it is empty.
- **required**: Indicates whether the `<textarea>` must be filled out before submitting the form.

## Commands

- **setTextarea**: Sets the `<textarea>` node with given attributes.
```typescript
  editor.commands.setTextarea({ name: 'description', rows: '4', cols: '50', placeholder: 'Enter text here', required: true });
```

- **toggleTextarea:** Toggles the `<textarea>` node with given attributes.
```typescript
  editor.commands.toggleTextarea({ name: 'description', rows: '4', cols: '50', placeholder: 'Enter text here', required: true });
```

- **unsetTextarea:** Unsets the `<textarea>` node
```typescript
 editor.commands.unsetTextarea();
```

## Usage Example

```typescript
import { Textarea } from '@fusion/extension-textarea';

const editor = new Editor({
  extensions: [
    Textarea.configure({
      HTMLAttributes: {
        class: 'my-textarea-class',
      },
    }),
  ],
});
```

## HTML Output Example

```html
<textarea id="story" name="story" rows="5" cols="33">
It was a dark and stormy night...
</textarea>
```