# Superscript Extension for Fusion Editor - @fusion/extension-superscript

## Overview

The `Superscript` extension allows you to apply superscript formatting to text within the Fusion Editor. Superscript text is typically used to display text slightly above the normal line of text, such as in mathematical exponents.

## Features

- Apply superscript formatting to selected text.
- Toggle superscript formatting on and off.
- Customize the HTML attributes applied to the `<sup>` element.

## Attributes

- **HTMLAttributes**: HTML attributes to add to the `<sup>` element.
  - **Default:** `{}`
  - **Example:** `{ class: 'superscript-text' }`

## Commands

- **setSuperscript**: Applies superscript formatting to the selected text.
  - **Usage:** `editor.commands.setSuperscript()`
- **toggleSuperscript**: Toggles superscript formatting on or off for the selected text.
  - **Usage:** `editor.commands.toggleSuperscript()`
- **unsetSuperscript**: Removes superscript formatting from the selected text.
  - **Usage:** `editor.commands.unsetSuperscript()`

## Configuration

- **HTMLAttributes**: Configure the attributes to be added to the `<sup>` tag.

## Keyboard Shortcuts

- **Mod-.**: Toggles superscript formatting.

## Customization

- You can customize the HTML attributes that are added to the `<sup>` tag by passing them through the `HTMLAttributes` option.

## Usage Example

To use the `Superscript` extension, include it in your editor setup:

```typescript
import { Superscript } from '@fusion/extension-superscript'

const editor = new Editor({
  extensions: [
    // other extensions
    Superscript,
  ],
})
```

## HTML Output Example

```html
<p>The <em>Pythagorean theorem</em> is often expressed as the following equation:</p>

<p>
  <var>a<sup>2</sup></var> + <var>b<sup>2</sup></var> = <var>c<sup>2</sup></var>
</p>
```