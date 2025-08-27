# Var Extension for Fusion Editor - @fusion/extension-var

## Overview

The `Var` extension allows you to mark text as a variable using the `<var>` element, typically used to represent variables in mathematical expressions or programming contexts within the Fusion Editor.

## Features

- **Inline Mark:** Renders the `<var>` element as an inline mark.
- **Command Integration:** Provides commands to set, toggle, and unset variable marks.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<var>` element.

## Commands

- **setVar:** Applies the `<var>` mark to selected text.
- **toggleVar:** Toggles the `<var>` mark on or off.
- **unsetVar:** Removes the `<var>` mark from selected text.

## Configuration

### Default Configuration

- **Name:** `var`
- **Inline:** The extension is applied as an inline mark.
- **Parse HTML:** Recognizes `<var>` tags when parsing HTML input.
- **Render HTML:** Outputs `<var>` tags with any additional HTML attributes.

## Customization

You can customize the `Var` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Var } from '@fusion/extension-var';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Var, /* other extensions */],
});
```

## HTML Output Example 
```html
<p>
  The volume of a box is <var>l</var> × <var>w</var> × <var>h</var>, where <var>l</var> represents the length,
  <var>w</var> the width and <var>h</var> the height of the box.
</p>
```
