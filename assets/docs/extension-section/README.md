# Section Extension for Fusion Editor - @fusion/extension-section

## Overview

The `Section` extension allows you to insert a `<section>` element within the Fusion Editor. This extension is useful for defining sections of your document, which are thematically grouped content blocks.

## Features

- **Block Node:** Renders the `<section>` element as a block node to group related content.
- **Command Integration:** Provides commands to insert a section element with customizable attributes.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<section>` element using the `HTMLAttributes` option.
- **id:** Specifies a unique ID for the section element.

## Commands

- **setSection:** Inserts a section element at the current cursor position.
```typescript
editor.commands.setSection({ id: 'section1' });
```

## Configuration
### Default Configuration
- **Name:** section
- **Block:** The extension is applied as a block node.
- **Content:** Accepts one or more block elements within the section.
- **Parse HTML:** Recognizes <section> tags and their attributes when parsing HTML input.
- **Render HTML:** Outputs <section> tags with any additional HTML attributes.

## Usage Example

```typescript
import { Section } from '@fusion/extension-section';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Section, /* other extensions */],
});
```

## HTML Output Example

```html
<section id="section1">
  <h2>Section Title</h2>
  <p>This is some content inside a section.</p>
</section>
```