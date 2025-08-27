# Button Extension for Fusion Editor - @fusion/extension-button

## Overview

The `Button` extension provides support for `<button>` elements in Fusion Editor. This extension allows you to create and manage buttons, which can be used for various interactive elements within the editor. The extension is designed to work seamlessly with other inline content and can be customized with various attributes.

## Features

- **Button Element Support:** Enables the use of `<button>` elements to create interactive content.
- **Customizable HTML Attributes:** Allows customization of HTML attributes for buttons, such as `class`, `type`, `id`, etc.
- **Content Handling:** Supports inline content inside the button.
- **Keyboard Shortcuts:** Provides a default keyboard shortcut for toggling buttons.

## Configuration

### Default Configuration

The `Button` extension comes with sensible defaults that are suitable for most use cases. Here’s a breakdown of its configuration:

- **Name:** `button` or `inlineButton`
- **Group:** `inline` or `block`
- **Content:** `inline*` (Allows inline content, such as text or icons, to be placed inside the button.)
- **Parse HTML:** Recognizes `<button>` tags when parsing HTML input.
- **Render HTML:** Outputs `<button>` tags with any additional HTML attributes.
- **Selectable:** `true` (Allows the button to be selected.)
- **Inline:** `true` (The button is treated as inline content.)
- **Atom:** `false` (The button can contain other inline content.)

### Example Usage

```typescript
import { Button } from '@fusion/extension-button';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Button.configure({ HTMLAttributes: { class: 'btn-primary' } }), // It's Optional to set HTMLAttributes
    InlineButton,
    /* other extensions */
  ],
});
```

## HTML Output

```html
<p>Click this <button class="btn-primary" type="button">Button</button> for action.</p>
```

## Commands

### For Button

- **setButton:** Creates a new button node with the specified attributes.

```typescript
editor.commands.setButton({ class: 'btn-primary', type: 'submit' });
```

- unsetButton: Removes the button node.
```typescript
editor.commands.unsetButton();
```

### For Inline Button

- **setInlineButton:** Creates a new button node with the specified attributes.

```typescript
editor.commands.setInlineButton({ type: 'button' });
```

- unsetInlineButton: Removes the button node.
```typescript
editor.commands.unsetInlineButton();
```

- **toggleButton:** Toggles the button node on or off.

```typescript
editor.commands.toggleInlineButton();
```