# `<nav>` Extension for Fusion Editor - @fusion/extension-nav

## Overview

The `<nav>` extension allows you to include navigational links in the Fusion Editor. This extension is useful for structuring sections that link to other parts of the site or page, typically containing a list of navigation links.

## Features

- **Semantic Navigation:** Provides the ability to create semantic navigation bars or sections within your content.
- **Flexible Content:** Supports block-level content like lists and headings inside the `<nav>` tag.
- **Customizable Attributes:** Add custom attributes to the `<nav>` tag for enhanced flexibility.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<nav>` element using the `HTMLAttributes` option.

## Commands

- **insertNav:** Inserts a `<nav>` element into the document.

## Configuration

### Default Configuration

- **Name:** `nav`
- **Group:** The extension is applied as a block-level node.
- **Content:** The extension can contain block-level content.
- **Parse HTML:** Recognizes `<nav>` tags when parsing HTML input.
- **Render HTML:** Outputs `<nav>` tags with any additional HTML attributes.

## Customization

You can customize the `<nav>` extension by passing in content or attributes through the `insertNav` command.

## Usage Example

```typescript
import { NavExtension } from '@fusion/extension-nav';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [NavExtension, /* other extensions */],
});

// Insert a <nav> element
editor.commands.insertNav({
  content: [
    { type: 'paragraph', content: [{ type: 'text', text: 'Home' }] },
    { type: 'paragraph', content: [{ type: 'text', text: 'About' }] }
  ]
});
```

## HTML Output Example
```html
<nav>
  <p>Home</p>
  <p>About</p>
</nav>
```