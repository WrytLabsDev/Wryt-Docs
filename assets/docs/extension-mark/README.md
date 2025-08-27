# Mark Extension for Fusion Editor - @fusion/extension-mark

## Overview

The `Mark` extension allows you to insert `<mark>` elements to highlight text within the Fusion Editor. The `<mark>` tag is used to highlight parts of text that are of relevance to the user.

## Features

- **Inline Node:** Renders the `<mark>` tag as an inline node to highlight text.
- **Command Integration:** Provides a command to insert the mark element with specific attributes such as `class` and `id`.
- **HTML Attributes:** Supports attributes such as `class` and `id` for the `<mark>` element.

## Attributes

- **class:** Adds custom classes to the `<mark>` element.
- **id:** Assigns an ID to the `<mark>` element for identification.

## Commands

- **insertMark:** Inserts a `<mark>` element with the specified attributes and content.

## Configuration

### Default Configuration

- **Name:** `mark`
- **Inline:** The extension is applied as an inline node.
- **Parse HTML:** Recognizes the `<mark>` tag and its attributes when parsing HTML input.
- **Render HTML:** Outputs a `<mark>` tag with the provided attributes and content.

## Customization

You can customize the `Mark` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Mark } from '@fusion/extension-mark';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Mark, /* other extensions */],
});
```

## HTML Output Example
```html
<p>This is <mark class="highlight">highlighted</mark> text.</p>
```