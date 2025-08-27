
# Optgroup Extension for Fusion Editor - @fusion/extension-optgroup

## Overview

The `Optgroup` extension allows you to group related `<option>` elements within a `<select>` dropdown in the Fusion Editor. This extension is useful for organizing long lists of options into manageable categories.

## Features

- **Block Node:** Renders the `<optgroup>` element as a block node to group `<option>` elements within a `<select>` dropdown.
- **Command Integration:** Provides commands to set and unset the `<optgroup>` node.
- **Attributes:** Supports attributes like `label` and `disabled` to customize the behavior of the `<optgroup>` element.

## Attributes

- **label:** Sets the label for the group of options.
- **disabled:** Disables the group of options, preventing user interaction.
- **HTML Attributes:** Customize the HTML attributes of the `<optgroup>` element using the `HTMLAttributes` option.

## Commands

- **setOptgroup:** Applies the `<optgroup>` node to wrap `<option>` elements.
- **unsetOptgroup:** Removes the `<optgroup>` node.

## Configuration

### Default Configuration

- **Name:** `optgroup`
- **Content:** The node contains `<option>` elements.
- **Group:** The extension is applied as a block node.
- **Parse HTML:** Recognizes `<optgroup>` tags and their attributes when parsing HTML input.
- **Render HTML:** Outputs `<optgroup>` tags with any additional HTML attributes.

## Usage Example

```typescript
import { Optgroup } from '@fusion/extension-optgroup';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Optgroup, /* other extensions */],
});
```

## HTML Output Example

```html
<label for="dino-select">Choose a dinosaur:</label>
<select id="dino-select">
  <optgroup label="Theropods">
    <option>Tyrannosaurus</option>
    <option>Velociraptor</option>
    <option>Deinonychus</option>
  </optgroup>
  <optgroup label="Sauropods">
    <option>Diplodocus</option>
    <option>Saltasaurus</option>
    <option>Apatosaurus</option>
  </optgroup>
</select>
```
