# Link Extension

## Overview
The `<link>` element defines a relationship between the current document and an external resource. It is most commonly used to link stylesheets, prefetch resources, or to define other kinds of document relationships. This extension supports creating and managing external resource links within a document.

## Features
- Supports the most common attributes of the `<link>` tag, including `href`, `rel`, `type`, `media`, `hreflang`, `sizes`, `as`, `crossorigin`, and `referrerpolicy`.
- Allows the insertion of external resources like stylesheets and other linked resources in the document.
- Allows dynamic customization of these attributes through commands.

## Tech Summary
The `<link>` tag is used to define relationships to external resources, usually in the `<head>` section of an HTML document. It is used for various purposes like linking stylesheets (`rel="stylesheet"`), icons, and preloaded resources.

## Attributes
- **href**: The URL of the linked resource.
- **rel**: Specifies the relationship between the current document and the linked resource (e.g., `stylesheet`, `icon`, `preload`).
- **type**: Specifies the MIME type of the linked resource.
- **media**: Defines for which media (screen, print) the resource is optimized.
- **hreflang**: Specifies the language of the linked document.
- **sizes**: Defines icon sizes (used with rel="icon").
- **as**: Specifies the type of resource being fetched when `rel="preload"`.
- **crossorigin**: Indicates how the linked resource should be fetched (for CORS).
- **referrerpolicy**: Specifies how much referrer information should be included when fetching the resource.

## Commands

### Set Link
```typescript
this.editor.commands.setLink({
  href: 'https://example.com/styles.css',
  rel: 'stylesheet',
  type: 'text/css',
  media: 'screen',
  crossorigin: 'anonymous',
  referrerpolicy: 'no-referrer'
})
```

## Configuration
```typescript
const editor = new Editor({
  extensions: [
    ExternalLink
  ],
});
```

### Usage Example

```typescript
this.editor.commands.setLink({
  href: 'https://example.com/styles.css',
  rel: 'stylesheet',
  media: 'screen',
  crossorigin: 'anonymous',
  referrerpolicy: 'no-referrer'
})
```

```html
<link rel="stylesheet" href="https://example.com/styles.css" media="screen" crossorigin="anonymous" referrerpolicy="no-referrer">
```


