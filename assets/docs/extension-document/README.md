# Fusion Document extension -  @fusion/extension-document

The Document extension is a fundamental component of the Fusion Editor, defining the top-level node of your document. It serves as the root container for all other nodes within the editor.

## Overview
The Document extension is essential for structuring the editor's content. It is analogous to the `<body>` tag in an HTML document, acting as the primary container for all other nodes. The Document node is configured to be a top-level node and can contain multiple block-level nodes.

## Spec

- Top-Level Node: This extension is set as the top node (topNode: true), meaning it serves as the root of the document.
- Content: The Document node can contain one or more block-level nodes (block+).

## Example

```typescript
import { Editor } from '@fusion/core'
import { Document } from '@fusion/extension-document'
import { Paragraph } from '@fusion/extension-paragraph'
import { Text } from '@fusion/extension-text'

const editor = new Editor({
  extensions: [
    Document,
    Paragraph,
    Text,
    // other extensions
  ],
})
```

The Document extension is a crucial part of the Fusion Editor, providing the root structure for your content. By including it in your editor setup, you enable the editor to manage and render multiple block-level elements effectively.
