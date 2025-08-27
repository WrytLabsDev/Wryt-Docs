# Template Extension for Fusion Editor - @fusion/extension-template

## Overview

The `Template` extension adds support for the HTML `<template>` tag within the Fusion Editor. This allows you to work with template elements, which are used to define content that is not rendered when the page loads but can be instantiated later via JavaScript.

## Features

- Allows for the inclusion and manipulation of `<template>` tags.
- Supports HTML attributes configuration.

## Attributes

- `HTMLAttributes`: HTML attributes to add to the `<template>` element.
  - **Default:** `{}` 
  - **Example:** `{ class: 'my-template' }`

## Commands

- `setTemplate`: Adds a `<template>` node.
  - **Usage:** `editor.commands.setTemplate()`
- `toggleTemplate`: Toggles a `<template>` node.
  - **Usage:** `editor.commands.toggleTemplate()`
- `unsetTemplate`: Removes a `<template>` node.
  - **Usage:** `editor.commands.unsetTemplate()`

## Configuration

- **HTMLAttributes:** Configure the attributes to be added to the `<template>` tag.

## Keyboard Shortcuts (If any)

- No default keyboard shortcuts are defined for this extension.

## Customization (Optional) (If any)

- Customize HTML attributes as needed for specific requirements.

## Usage Example

To use the `Template` extension, include it in your editor setup:

```typescript
import { Template } from '@fusion/extension-template'

const editor = new Editor({
  extensions: [
    // other extensions
    Template,
  ],
})
```

## HTML Output Example

```html
<template class="my-template">
  <!-- Template content goes here -->
</template>
```