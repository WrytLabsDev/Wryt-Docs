# Article Extension for Fusion Editor - @fusion/extension-article

## Overview

The `Article` extension provides support for the `<article>` element in Fusion Editor. The `<article>` tag is a semantic element that represents a self-contained composition in a document, page, application, or site. This extension ensures that your content is well-structured and semantically meaningful, which is beneficial for both accessibility and SEO.

The <article> element is designed for content that is self-contained and independently distributable. This can include blog posts, news stories, comments, and other similar types of content.

## Features

- **Semantic Structure:** Supports the `<article>` tag, allowing for better content organization.
- **Customizable HTML Attributes:** Allows customization of attributes for the `<article>` tag.
- **Nested Articles:** Supports nested `<article>` elements for complex content structures.
- **Automatic Handling:** Automatically handles permitted content and parents, ensuring valid HTML structure.

## Configuration

### Default Configuration

The `Article` extension is configured with the following defaults:

- **Name:** `article`
- **Group:** `block`
- **Content:** `block+`
- **Parse HTML:** Recognizes and processes `<article>` tags when parsing HTML input.
- **Render HTML:** Outputs `<article>` tags with any additional HTML attributes.
- **Priority:** `1000`

### Commands

This extension provides a command to toggle the article element:

```typescript
// Setting an article node
editor.commands.setArticle({ class: 'my-article', id: 'article1' });

// Unsetting an article node
editor.commands.unsetArticle();
```

### Example

Here’s how to use the `Article` extension in your Fusion Editor setup:

```typescript
import { Article } from '@fusion/extension-article';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Article,
    // other extensions...
  ],
});
```

### HTML Output Example

```html
<article>
  <h1>Article Title</h1>
  <p>This is the content of the article.</p>
</article>
```

