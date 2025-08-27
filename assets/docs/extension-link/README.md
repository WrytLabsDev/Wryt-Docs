# Link Extension for Tiptap - @fusion/extension-link

The `Link` extension allows you to create and manage hyperlinks in the Fusion Editor. Built on top of Tiptap, this extension provides extensive functionality for handling links, including autolinking, custom protocols, and advanced validation to prevent XSS attacks.

## Installation

To install the Link extension, you can use npm or yarn:

```bash
npm install @fusion/extension-link

Or

yarn add @tiptap/core
```

## Usage

```typescript
import { Link } from '@fusion/extension-link';

const editor = new Editor({
  extensions: [
    Link.configure({
      openOnClick: true,
      linkOnPaste: true,
      autolink: true,
      protocols: ['ftp', 'git'], // Add custom protocols if needed
      defaultProtocol: 'http',
      HTMLAttributes: {
        target: '_blank',
        rel: 'noopener noreferrer nofollow',
      },
      validate: (url) => !!url, // Validation function for links
    }),
    // other extensions...
  ],
});
```

## Features

- **Auto Linking:** Automatically add links as you type.
- **Custom Protocols:** Support for custom protocols like ftp, git, etc.
- **Link Validation:** Prevents XSS attacks by validating the URL.
- **Click to Open:** Opens links on click when the editor is not in editable mode.
- **Paste Handling:** Automatically adds links to pasted content if it contains a valid URL.

## Options

- **autolink:** Automatically add links as you type. Default is true.
- **protocols:** Array of custom protocols to be registered with linkifyjs.
- **defaultProtocol:** Default protocol to use when no protocol is specified. Default is http.
- **openOnClick:** Opens links on click. Default is true.
- **linkOnPaste:** Adds a link to the current selection if the pasted content only contains a URL. Default is true.
- **HTMLAttributes:** Additional HTML attributes to add to the link element. By default, it adds target, rel, and class.
- **validate:** A validation function to modify link verification for the auto linker.

## Attributes
- **href:** The URL to which the link points.
- **target:** Specifies where to open the linked document. Default is _blank.
- **rel:** Specifies the relationship between the current document and the linked document. Default is noopener noreferrer nofollow.
- **class:** Specifies one or more class names for the link.

## Commands

- **setLink:** Sets a link mark with specified attributes.
- **toggleLink:** Toggles a link mark with specified attributes.
- **unsetLink:** Removes the link mark.

## Security

- This extension includes validation to prevent XSS attacks by filtering out potentially dangerous URLs.

## Example

- Here's an example of setting up the Link extension with custom protocols and validation:

```typescript
import { Editor } from '@tiptap/core';
import { Link } from './path-to-your-extension';

const editor = new Editor({
  extensions: [
    Link.configure({
      autolink: true,
      defaultProtocol: 'https',
      HTMLAttributes: {
        target: '_blank',
        rel: 'noopener noreferrer',
      },
    }),
  ],
  content: `
    <p>This is a paragraph with a <a href="https://tiptap.dev" class="example-class">link to Tiptap</a>.</p>
    <p>Another link: <a href="mailto:example@example.com">Send Email</a></p>
  `,
});
```

## Priority

The Link extension has a priority of 1000 to ensure it takes precedence in scenarios where there might be conflicts with other inline-level extensions. This can be important for maintaining consistent behavior in the editor when dealing with different types of content and formatting.

## HTML Output

Here's what the HTML output might look like after rendering content with the Link extension:

```html 
<p>This is a paragraph with a 
   <a href="https://tiptap.dev" target="_blank" rel="noopener noreferrer" class="example-class">link to Tiptap</a>.
</p>

<p>Another link: 
   <a href="mailto:example@example.com" target="_blank" rel="noopener noreferrer">Send Email</a>
</p>
```
