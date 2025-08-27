# Ruby Extension for Fusion Editor - @fusion/extension-ruby

## Overview

The `Ruby` extension allows you to add ruby annotations (small text above or beside the base text) within the Fusion Editor. Ruby annotations are typically used in East Asian typography to show the pronunciation of characters.

## Features

- **Inline Node:** Renders the `<ruby>` element as an inline node to display ruby annotations.
- **Command Integration:** Provides commands to set the ruby node.
- **Customizable HTML Attributes:** Supports passing custom HTML attributes to the `<ruby>` element.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<ruby>` element using the `HTMLAttributes` option.

## Commands

- **setRuby:** Applies the ruby node to the selected text.
```typescript
editor.commands.setRuby();
```

## Configuration

## Default Configuration

- **Name:** ruby
- **Inline:** The extension is applied as an inline node.
- **Parse HTML:** Recognizes <ruby> tags when parsing HTML input.
- **Render HTML:** Outputs <ruby> tags with any additional HTML attributes.

## Usage Example

```typescript
import { Ruby } from '@fusion/extension-ruby';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Ruby, /* other extensions */],
});

```

## HTML Output Example

```html
<ruby> 明日 <rp>(</rp><rt>Ashita</rt><rp>)</rp> </ruby>
```