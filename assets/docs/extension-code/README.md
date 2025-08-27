# Code Extension for Fusion Editor - @fusion/extension-code

## Overview

The `Code` extension enables the use of inline `<code>` elements in Fusion Editor. This extension is particularly useful for representing code snippets or any text that should be displayed in a monospaced font without interpretation by the browser as HTML.

## Features

- **Inline Code Support:** Allows you to wrap text in `<code>` tags to display inline code snippets.
- **Preservation of HTML Entities:** Ensures that HTML entities within the code snippet are not parsed as HTML.
- **Customizable HTML Attributes:** Provides the ability to add custom attributes to the `<code>` element.

## Technical Summary

### Content Categories

- **Phrasing content**: The code element is part of the phrasing content category and can be used where phrasing content is expected.
- **Flow content**: The code element can also be used within flow content, but only where phrasing content is allowed.
- **Palpable content**: The code element is perceivable by the user and contributes to the document's meaning.

### Attributes

- **Global attributes**: The code element supports all global attributes.
- **No Additional Attributes**: The code element itself does not have any specific attributes beyond the global ones.

### Commands
- **setCode:** Wraps the selected text in a <code> element or inserts a new one at the cursor.

```typescript
editor.commands.setCode();
```

- **toggleCode:** Toggles the <code> element on or off.
```typescript
editor.commands.toggleCode();
```

- **unsetCode:** Removes the <code> element.
```typescript
editor.commands.unsetCode();
```

### Keyboard Shortcuts
- **Mod-e:** Toggles the code element.

### Customization (Optional)
```typescript
Code.configure({
  HTMLAttributes: { class: 'inline-code' },
});
```

## Configuration

### Default Configuration

The `Code` extension comes pre-configured with default options that are suitable for most use cases. Below is a summary of its configuration:

- **Name:** `code`
- **Group:** `inline`
- **Content:** Inline code can only contain text and does not allow nested inline elements.
- **Parse HTML:** The extension identifies `<code>` tags during the HTML parsing process.
- **Render HTML:** Outputs a `<code>` element with any specified HTML attributes.

### Example Usage

```typescript
import { Code } from '@fusion/extension-code';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Code.configure({ HTMLAttributes: { class: 'inline-code' } }),
    /* other extensions */
  ],
});
```

### HTML Output

```html
<code class="inline-code">exampleCode()</code>
```
