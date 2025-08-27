# Subscript Extension for Fusion Editor - @fusion/extension-subscript

## Overview

The `Subscript` extension allows you to apply subscript formatting to text within the Fusion Editor. Subscript text is typically used to display text slightly below the normal line of text, such as in chemical formulas or mathematical notations.

## Features

- Apply subscript formatting to selected text.
- Toggle subscript formatting on and off.
- Customize the HTML attributes applied to the `<sub>` element.

## Attributes

- **HTMLAttributes**: HTML attributes to add to the `<sub>` element.
  - **Default:** `{}`
  - **Example:** `{ class: 'subscript-text' }`

## Commands

- **setSubscript**: Applies subscript formatting to the selected text.
  - **Usage:** `editor.commands.setSubscript()`
- **toggleSubscript**: Toggles subscript formatting on or off for the selected text.
  - **Usage:** `editor.commands.toggleSubscript()`
- **unsetSubscript**: Removes subscript formatting from the selected text.
  - **Usage:** `editor.commands.unsetSubscript()`

## Configuration

- **HTMLAttributes**: Configure the attributes to be added to the `<sub>` tag.

## Keyboard Shortcuts

- **Mod-,**: Toggles subscript formatting.

## Customization

- You can customize the HTML attributes that are added to the `<sub>` tag by passing them through the `HTMLAttributes` option.

## Usage Example

To use the `Subscript` extension, include it in your editor setup:

```typescript
import { Subscript } from '@fusion/extension-subscript'

const editor = new Editor({
  extensions: [
    // other extensions
    Subscript,
  ],
})
```

## HTML Output Example

```html
<p>
  Almost every developer's favorite molecule is C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>, also known as
  "caffeine."
</p>
```