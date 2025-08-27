# Cite Extension for Fusion Editor - @fusion/extension-cite

## Overview

The `Cite` extension provides support for `<cite>` elements in Fusion Editor. This extension allows you to create and manage citations in your content, typically used to reference the title of a work, such as a book, article, or play.

## Features

- **Cite Element Support:** Enables the use of `<cite>` elements to add citations to your content.
- **Customizable HTML Attributes:** Allows customization of HTML attributes for the cite, such as `class`, `id`, etc.
- **Content Handling:** The cite element can contain text and other inline elements.
- **Keyboard Shortcuts:** Provides a default keyboard shortcut for toggling cite elements.

## Technical Summary

### Content Categories

- **Phrasing content**: The cite element is part of the phrasing content category and can be used where phrasing content is expected.
- **Flow content**: The cite element can be used in places where flow content is accepted.
- **Palpable content**: The cite element is perceivable by the user and contributes to the document's meaning.

### Attributes

- **Global attributes**: The cite element supports all global attributes.

### Commands

- **setCite:** Creates a new cite node with the specified attributes.
```typescript
editor.commands.setCite({ class: 'citation' });
```

- **toggleCite:** Toggles the cite node on or off.
```typescript
editor.commands.toggleCite({ class: 'citation' });
```

- **unsetCite:** Removes the cite node.
```typescript
editor.commands.unsetCite();
```

## Configuration

### Default Configuration

The `Cite` extension comes with sensible defaults that are suitable for most use cases. Here’s a breakdown of its configuration:

- **Name:** `cite`
- **Group:** `inline`
- **Content:** `inline*` (Allows text and inline elements inside the cite.)
- **Parse HTML:** Recognizes `<cite>` tags when parsing HTML input.
- **Render HTML:** Outputs `<cite>` tags with any additional HTML attributes.

### Example Usage

```typescript
import { Cite } from '@fusion/extension-cite';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Cite.configure({ HTMLAttributes: { class: 'citation' } }),
    /* other extensions */
  ],
});
```

### HTML Output

```html
<cite class="citation">Example Citation</cite>
```