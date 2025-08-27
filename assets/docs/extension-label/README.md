# Label and InlineLabel Extensions for Fusion Editor - @fusion/extension-label

## Overview

The `Label` and `InlineLabel` extensions allow you to add and manage `<label>` elements in Fusion Editor. These extensions support block-level and inline label usage, offering flexibility for associating labels with form elements.

- **Label Extension**: For block-level labels that typically associate with form controls.
- **InlineLabel Extension**: For inline labels, useful when the label needs to be part of the text flow.

## Features

### Label (Block-level)
- **Block-level Node:** Inserts a `<label>` element used to associate a label with form controls.
- **Customizable:** Supports common attributes such as `for`, `class`, and `id`.
- **Command Integration:** Provides commands for inserting and managing block-level label nodes.
- **Draggable:** Can be moved within the editor.
- **Atom Node:** Treated as a single element in the document.

### InlineLabel
- **Inline-level Node:** Allows the insertion of inline `<label>` elements, enabling label usage within text content.
- **Customizable:** Supports attributes such as `name`, `type`, `class`, `id`, and more.
- **Command Integration:** Provides commands for setting, toggling, and unsetting inline label nodes.

## Attributes

### Label (Block-level)
- **for**: Specifies which form element a label is bound to.
- **class**: Assigns CSS classes to the label element.
- **id**: Unique identifier for the label element.

### InlineLabel
- **name**: Specifies the name attribute of the label.
- **type**: Defines the type of label.
- **value**: Value of the label.
- **class**: Assigns CSS classes.
- **id**: Unique identifier for the inline label.

## Commands

### Block-level Label

```typescript
editor.commands.insertLabel({
  attrs: { for: 'input-id', class: 'label-class' },
  content: 'Your Label',
});
```

- **insertLabel:** Inserts a block-level label element with specified attributes and content. 
- **setInlineLabel:** Sets an inline label element with given attributes.
- **toggleInlineLabel:** Toggles between an inline label and a paragraph.
- **unsetInlineLabel:** Removes the inline label node.

## Usage Example

### Block-level Label

```typescript
editor.commands.insertLabel({
  attrs: { for: 'input-id', class: 'label-class' },
  content: 'Username',
});
```

### InlineLabel

```typescript
editor.commands.setInlineLabel({
  name: 'inline-label',
  class: 'label-inline-class',
});
```

## Configuration
```typescript
const editor = new Editor({
  extensions: [
    Label.configure({
      HTMLAttributes: { // Optional
        class: 'my-label',
      },
    }),
    InlineLabel.configure({
      HTMLAttributes: { // Optional
        class: 'my-inline-label',
      },
    }),
  ],
});
```

## HTML Output Example

##### Label (Block-level)
```html
<label for="input-id" class="label-class">Username</label>
```

##### InlineLabel
```html
<p><label class="label-inline-class">Label Text</label></p>
```