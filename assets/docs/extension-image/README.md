# Fusion Image extensions - @fusion/extension-image

The `@fusion/extension-image` package provides two powerful extensions for handling image nodes in your Fusion Editor: `Image` and `InlineImage`. These extensions allow for versatile rendering of images, whether they are standalone block elements or inline elements within text.


## Installation

To install the `Image` extension, use npm or yarn:

```bash
npm install @fusion/extension-image
# or
yarn add @fusion/extension-image
```

## Usage

### Importing Extensions (Combined)

```typescript
import { Image, InlineImage } from '@fusion/extension-image';

const editor = new Editor({
  extensions: [
    Image,
    InlineImage,
    // other extensions...
  ],
  content: `
    <div>
      <p>This is a paragraph with an inline image <img src="https://interactive-examples.mdn.mozilla.net/media/cc0-images/grapefruit-slice-332-332.jpg" alt="Grapefruit slice atop a pile of other slices" /> inside it.</p>
      <img src="https://interactive-examples.mdn.mozilla.net/media/cc0-images/grapefruit-slice-332-332.jpg" alt="Grapefruit slice atop a pile of other slices" />
    </div>
  `,
});
```

## HTML Input and Output Example for Combined
```html
<div>
  <p>This is a paragraph with an inline image <img src="https://interactive-examples.mdn.mozilla.net/media/cc0-images/grapefruit-slice-332-332.jpg" alt="Grapefruit slice atop a pile of other slices" /> inside it.</p>
  <img src="https://interactive-examples.mdn.mozilla.net/media/cc0-images/grapefruit-slice-332-332.jpg" alt="Grapefruit slice atop a pile of other slices" />
</div>
```

### Input Rules Or Markdown
```markdown
![Image Alt Text](https://example.com/image.jpg)
```

### Configuration Options

- `inline (boolean):` Default is true. This configures the image as an inline element.
- `allowBase64 (boolean):` Default is true. This option enables or disables the ability to insert base64-encoded images.
- `HTMLAttributes (object):` Default attributes to be applied to the image element.

## Block Image  

The Block Image (Just import `Image`) provides functionality for adding and rendering block images in the Fusion editor. This extension handles images that are not within a paragraph, ensuring they are displayed as block elements.

```typescript
import { Image } from '@fusion/extension-image';

const editor = new Editor({
  extensions: [
    Image.configure({
      inline: false,  // By default, this extension handles block-level images.
      allowBase64: true,  // Enables support for base64-encoded images.
      HTMLAttributes: {
        class: 'fit-picture', // Optional: Define default class or other attributes.
      },
    }),
    // Other extensions...
  ],
});
```

## HTML Output Example

```html
<div>
  <img
    class="fit-picture"
    src="https://example.com/image.jpg"
    alt="An example image" />
</div>
```

## Inline Image - @fusion/extension-inline-image

The InlineImage (Just import `InlineImage`) allows you to insert and manipulate inline images within your text content. These images are treated as inline elements and can be wrapped inside paragraphs or other inline-level containers.

## Usage

```typescript
import { InlineImage } from '@fusion/extension-inline-image';

const editor = new Editor({
  extensions: [
    InlineImage.configure({
      inline: true,  // This extension handles inline images.
      allowBase64: true,  // Enables support for base64-encoded images.
      HTMLAttributes: {
        class: 'fit-picture', // Optional: Define default class or other attributes.
      },
    }),
    // Other extensions...
  ],
});
```

### HTML Output Example

```html
<p>This is an inline image: <img
  class="fit-picture"
  src="https://example.com/image.jpg"
  alt="An example image" /></p>
```
Both Image and InlineImage extensions can be customized to fit your needs. 

- Block images are rendered as standalone block elements.
- Inline images are rendered as inline elements within text.

The @fusion/extension-image package is a comprehensive solution for handling images in your Fusion Editor. By using both the Image and InlineImage extensions, you can ensure that images are rendered correctly based on their context, providing a consistent and visually appealing editing experience.
