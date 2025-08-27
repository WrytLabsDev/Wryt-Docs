# Aside Extension for Fusion Editor - @fusion/extension-aside

## Overview

The `Aside` extension provides support for the `<aside>` element in Fusion Editor. The `<aside>` tag is a semantic HTML element used to represent content that is tangentially related to the content around it. This can include sidebars, pull quotes, and other similar types of content. The extension ensures that your content is organized and semantically meaningful, which is beneficial for accessibility and SEO.

The `<aside>` element is designed for content that is related to the main content but can be considered separate. This is commonly used for sidebars, pull quotes, and similar content.

## Features

- **Semantic Structure:** Supports the `<aside>` tag, allowing for the inclusion of tangential content.
- **Customizable HTML Attributes:** Allows customization of attributes for the `<aside>` tag.
- **Content Organization:** Helps in structuring content that is related to the main content but can stand alone.
- **Automatic Handling:** Ensures that the `<aside>` element is used correctly within the document structure.

## Configuration

### Default Configuration

The `Aside` extension is configured with the following defaults:

- **Name:** `aside`
- **Group:** `block`
- **Content:** `block+`
- **Parse HTML:** Recognizes and processes `<aside>` tags when parsing HTML input.
- **Render HTML:** Outputs `<aside>` tags with any additional HTML attributes.
- **Priority:** `1000`

### Commands

```typescript
// Setting an aside node
editor.commands.setAside({ class: 'my-aside', id: 'aside1' });

// Unsetting an aside node
editor.commands.unsetAside();
```

### Example

Here’s how to use the `Aside` extension in your Fusion Editor setup:

```typescript
import { Aside } from '@fusion/extension-aside';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Aside,
    // other extensions...
  ],
});
```

### HTML Output

```html
<aside>
  <p>This is a sidebar or other tangential content.</p>
</aside>
```



