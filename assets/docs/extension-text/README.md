# Fusion Text Extenion - @fusion/extension-text

The `Text` extension enables the creation and manipulation of text nodes within the Fusion Editor. It is responsible for handling inline text content, allowing you to include and manage plain text within your documents.

## Overview

The `Text` extension is crucial for text-based content in the editor. It defines a node type for inline text, making it possible to insert and manage text within other inline or block-level nodes.

## Features

- **Inline Node:** This extension defines a node that belongs to the inline group (`group: 'inline'`). This means it is used for content that appears within other nodes and does not create block-level separations.

## Usage

This node is used to represent text within inline contexts, such as within paragraphs, headings, or other inline elements.

```typescript
import { Editor } from '@fusion/core'
import { Document } from '@fusion/extension-document'
import { Text } from '@fusion/extension-text'
import { Paragraph } from '@fusion/extension-paragraph'

const editor = new Editor({
  extensions: [
    Document,
    Text,
    Paragraph,
    // other extensions
  ],
})

```

The Text extension is a fundamental part of the Fusion Editor, enabling the insertion and management of inline text content. By including it in your editor setup, you ensure that text can be effectively handled and displayed alongside other content types.
