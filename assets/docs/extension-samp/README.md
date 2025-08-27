# Samp Extension for Fusion Editor - @fusion/extension-samp

## Overview

The `Samp` extension allows you to represent sample output from a computer program within the Fusion Editor. This extension is useful for including sample text or code output in your content.

## Features

- **Inline Node:** Renders the `<samp>` element as an inline node to display sample output.
- **Command Integration:** Provides commands to set the samp node.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<samp>` element using the `HTMLAttributes` option.

## Commands

- **setSamp:** Inserts a sample output node at the current position.
```typescript
editor.commands.setSamp();
```

## Configuration

### Default Configuration

- **Name:** samp
- **Inline:** The extension is applied as an inline node.
- **Parse HTML:** Recognizes <samp> tags when parsing HTML input.
- **Render HTML:** Outputs <samp> tags with any additional HTML attributes.

## Usage Example

```typescript
import { Samp } from '@fusion/extension-samp';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Samp, /* other extensions */],
});
```

## HTML Output Example

```html
<p>This is <samp>sample output</samp> text.</p>
```