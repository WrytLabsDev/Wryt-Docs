# Legend Extension for Fusion Editor - @fusion/extension-legend

## Overview

The `Legend` extension allows you to insert `<legend>` elements within the Fusion Editor. The `<legend>` tag defines a caption for the `<fieldset>` element, providing descriptive text for the grouped form controls.

## Features

- **Block Node:** Renders the `<legend>` tag as a block-level node.
- **Command Integration:** Provides a command to insert the `<legend>` element with optional attributes like `id` and `class`.
- **HTML Attributes:** Supports standard HTML attributes to customize the `<legend>` element.

## Attributes

- **class:** Adds custom classes to the `<legend>` element.
- **id:** Assigns an ID to the `<legend>` element for identification.

## Commands

- **insertLegend:** Inserts a `<legend>` element with the specified attributes and content.

## Configuration

### Default Configuration

- **Name:** `legend`
- **Block:** The extension is applied as a block-level node.
- **Parse HTML:** Recognizes the `<legend>` tag and its attributes when parsing HTML input.
- **Render HTML:** Outputs a `<legend>` tag with the provided attributes and content.

## Customization

You can customize the `Legend` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Legend } from '@fusion/extension-legend';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Legend, /* other extensions */],
});
```

## HTML Output Example
```html
<fieldset>
  <legend id="legend1" class="legend-class">Personal Information</legend>
  <input type="text" name="name" placeholder="Name">
</fieldset>
```