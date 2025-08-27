# Div Extension for Fusion Editor - extension-div

## Overview

The `Div` extension adds support for `<div>` elements in Fusion Editor. This extension allows you to create and manipulate `<div>` elements, which are commonly used for layout and grouping content in HTML. The extension is designed to be flexible, allowing for different content configurations based on your needs.

## Features

- **Block-Level Container:** By default, the `<div>` element can contain block-level elements such as paragraphs, headings, lists, and more.
- **Content Flexibility:** The extension can be configured to support either block-level or inline-level content.

## Configuration

The `Div` extension can be customized using the `content` property. Here’s how you can configure it:

### `content: 'block*'` (Current Setting)

- **Behavior:** 
  - The `<div>` acts as a block-level container, capable of holding other block-level elements.
  - Inline content (e.g., text) placed directly inside the `<div>` will be automatically wrapped in a paragraph (`<p>`), maintaining the block-level structure.
  
- **Usage:**
  - Use this configuration when you want to ensure that the content inside the `<div>` maintains a block-level structure.
  - Ideal for grouping block-level elements like paragraphs and headings.

### `content: 'inline*'` (Commented Out)

- **Behavior:**
  - The `<div>` allows text and inline elements to be placed directly inside it without wrapping them in a paragraph.
  - This configuration is useful for specific layouts where you want to avoid additional block-level wrappers.

- **Usage:**
  - Uncomment and use this setting if you need the `<div>` to act as a container for inline content without additional wrapping.
  - Note: This may result in less semantic HTML, as `<div>` is typically used for block-level content.

## Example

Here’s an example of how the `Div` extension can be used:

```typescript
import { Div } from './path/to/your/div-extension';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Div, /* other extensions */],
});
```

With content: 'block*':

```html
<div>
  <p>This is a paragraph inside a div.</p>
  <h2>This is a heading inside a div.</h2>
</div>
```
With content: 'inline*':

```html
<div>
  This is text directly inside the div.
  <span>Inline element inside the div.</span>
</div>
```



