# Fieldset Extension for Fusion Editor - @fusion/extension-fieldset

## Overview

The `Fieldset` extension allows you to insert `<fieldset>` elements within the Fusion Editor. The `<fieldset>` tag is used to group related elements in a form, providing a clear structure for form elements.

## Features

- **Block Node:** Renders the `<fieldset>` tag as a block-level node.
- **Command Integration:** Provides a command to insert the `<fieldset>` element with optional attributes like `id`, `class`, `disabled`, `form`, and `name`.
- **HTML Attributes:** Supports standard HTML attributes to customize the `<fieldset>` element.

## Attributes

- **disabled:** Specifies whether the `<fieldset>` is disabled, making all its elements unmodifiable.
- **form:** Associates the `<fieldset>` with a specific form.
- **name:** Assigns a name to the `<fieldset>`.
- **class:** Adds custom classes to the `<fieldset>` element.
- **id:** Assigns an ID to the `<fieldset>` element for identification.

## Commands

- **insertFieldset:** Inserts a `<fieldset>` element with the specified attributes and content.

## Configuration

### Default Configuration

- **Name:** `fieldset`
- **Block:** The extension is applied as a block-level node.
- **Parse HTML:** Recognizes the `<fieldset>` tag and its attributes when parsing HTML input.
- **Render HTML:** Outputs a `<fieldset>` tag with the provided attributes and content.

## Customization

You can customize the `Fieldset` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Fieldset } from '@fusion/extension-fieldset';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Fieldset, /* other extensions */],
});
```

## HTML Output Example
```html
<fieldset id="fieldset1" class="form-group" disabled>
  <legend>Personal Information</legend>
  <input type="text" name="name" placeholder="Name">
</fieldset>
```