# Del Extension for Fusion Editor - @fusion/extension-del

## Overview

The `Del` extension allows you to add the `<del>` tag in the Fusion Editor. The `<del>` tag represents text that has been deleted from a document.

## Features

- **Block-level Node:** Adds the `<del>` element for deleted content.
- **Command Integration:** Provides a command to insert the `<del>` element with attributes.
- **Attributes:** Supports common attributes such as `datetime` and `cite`.

## Attributes

- **datetime:** Represents the date and time of the deletion.
- **cite:** A URL providing the source for the deletion.

## Commands

- **insertDel:** Inserts the `<del>` element with optional attributes like `datetime` and `cite`.

## Configuration

### Default Configuration

- **Name:** `del`
- **Group:** `block`
- **Content:** Can contain inline elements.
- **Attributes:** Supports `datetime` and `cite` attributes.

## Customization

You can customize the `Del` extension by passing in HTML attributes through the `HTMLAttributes` option.

## Usage Example

```typescript
import { Del } from '@fusion/extension-del';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Del, /* other extensions */],
});
```

## HTML Output Example
```html
<p>This text is <del datetime="2023-09-16">deleted</del>.</p>
```