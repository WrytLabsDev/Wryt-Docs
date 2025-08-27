# Search Extension for Fusion Editor - @fusion/extension-search

## Overview

The `Search` extension allows you to include a `<search>` element within the Fusion Editor. This element is used to semantically represent search or filtering functionality within your content.

## Features

- **Block Node:** Adds a `<search>` element as a block-level node.
- **Command Integration:** Provides commands to insert a `<search>` element into the editor content.
- **Keyboard Shortcuts:** Insert a `<search>` element using keyboard shortcuts.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<search>` element using the `HTMLAttributes` option.

## Commands

- **setSearch:** Inserts a `<search>` element into the editor content.
```typescript
editor.commands.setSearch();
```

## Configuration

### Default Configuration

- **Name:** search
- **Group:** block
- **Content:** Accepts any flow content inside the <search> element.
- **Parse HTML:** Recognizes the <search> tag when parsing HTML input.
- **Render HTML:** Outputs the <search> tag with any additional HTML attributes.

## Usage Example

```typescript
import { Search } from '@fusion/extension-search';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Search, /* other extensions */],
});
```

## HTML Output Example

```html
<search>
  <form action="./search/">
    <label for="movie">Find a Movie</label>
    <input type="search" id="movie" name="q" />
    <button type="submit">Search</button>
  </form>
</search>

```