# Dfn Extension for Fusion Editor - @fusion/extension-dfn

## Overview

The `Dfn` extension provides support for the `<dfn>` HTML element in Fusion Editor. The `<dfn>` (definition) element is used to denote a term that is being defined within the context of an article or a document. This extension enables the user to mark specific terms with `<dfn>` to signify definitions.

## Features

- **Definition Tag Support:** Easily wrap important terms with the `<dfn>` tag to highlight their definitions.
- **Customizable HTML Attributes:** Supports customization of attributes like `title`.
- **Inline Element:** Acts as an inline element that can be inserted into paragraphs or other block-level elements.

## Configuration

### Default Configuration

The `Dfn` extension offers flexibility with the following defaults:

- **Name:** `dfn`
- **Group:** `inline`
- **Content:** `text*` (Only text content is allowed inside `<dfn>`.)
- **HTML Attributes:** `{}` (Custom HTML attributes for the `<dfn>` element.)

### Commands

- **setDfn:** Wraps the selected content inside a `<dfn>` tag.
  ```typescript
  editor.commands.setDfn({ title: 'definition' });
  ```

## Usage
```typescript
const editor = new Editor({
  extensions: [
    Dfn.configure({
      HTMLAttributes: { title: 'definition' },
    }),
  ],
});
```

## HTML Output
```html
<p>
  The <dfn><abbr title="Hubble Space Telescope">HST</abbr></dfn> is among the
  most productive scientific instruments ever constructed. It has been in orbit
  for over 20 years, scanning the sky and returning data and photographs of
  unprecedented quality and detail.
</p>
```