# Main Extension for Fusion Editor - @fusion/extension-main

## Overview

The `Main` extension allows you to insert `<main>` elements within the Fusion Editor. The `<main>` tag is used to represent the dominant content of a document, crucial for accessibility and structure.

## Features

- **Block Node:** Renders the `<main>` tag as a block-level node.
- **Command Integration:** Provides a command to insert the `<main>` element with optional attributes like `id` and `class`.
- **HTML Attributes:** Supports standard HTML attributes to customize the `<main>` element.

## Attributes

- **class:** Adds custom classes to the `<main>` element.
- **id:** Assigns an ID to the `<main>` element for identification.

## Commands

- **insertMain:** Inserts a `<main>` element with the specified attributes and content.

## Configuration

### Default Configuration

- **Name:** `main`
- **Block:** The extension is applied as a block-level node.
- **Parse HTML:** Recognizes the `<main>` tag and its attributes when parsing HTML input.
- **Render HTML:** Outputs a `<main>` tag with the provided attributes and content.

## Customization

You can customize the `Main` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Main } from '@fusion/extension-main';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Main, /* other extensions */],
});
```

### HTML Output Example
```html
<main id="main-section" class="content-main">
  <p>Main content goes here.</p>
</main>
```