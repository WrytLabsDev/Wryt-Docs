# Fusion Image Map Area Extension - extension-image-map-area

This extension provides support for the `<map>` and `<area>` HTML elements, allowing you to create and manage image maps within the Fusion editor. These elements are essential for defining interactive areas on images.

## Installation

To install the package, use the following command:

```bash
npm install @fusion/extension-map-area

# or
yarn add @fusion/extension-image
```

## Usage

Here’s how you can integrate the map and area extensions into your Fusion editor setup:

```typescript
import { MapExtension, AreaExtension } from '@fusion/extension-map-area';

const editor = new Editor({
  extensions: [
    // Other extensions...
    MapExtension,
    AreaExtension,
  ],
  content: `
    <p>This is an image with an associated image map:</p>
    <img src="image.png" usemap="#image-map" alt="An example image" />

    <map name="image-map">
      <area shape="rect" coords="34,44,270,350" href="https://example.com" alt="Example Area" />
    </map>
  `,
});
```

### Overview

The `<map>` extension allows you to define an image map in your content. An image map is a way to link different parts of an image to different destinations.

The `<area>` extension enables you to define clickable areas within an image map. Each area can have a different shape and destination.

Permitted Content: Transparent content, but must have one or more <area>, <link>, or other elements that define the interactive areas.

## Example Usage

```html
<!-- Photo by Juliana e Mariana Amorim on Unsplash -->
<map name="primary">
  <area
    shape="circle"
    coords="75,75,75"
    href="https://developer.mozilla.org/docs/Web/JavaScript"
    target="_blank"
    alt="JavaScript" />
  <area
    shape="circle"
    coords="275,75,75"
    href="https://developer.mozilla.org/docs/Web/CSS"
    target="_blank"
    alt="CSS" />
</map>
<img
  usemap="#primary"
  src="https://live.mdnplay.dev/en-US/docs/Web/HTML/Element/map/parrots.jpg"
  alt="350 x 150 picture of two parrots" />
```

**Note:** Your Image tag must have the `usemap` attribute and the same has to be refered in map tag `name` attr. 

- https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map
- https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area

You can create Image Map Area for Free at: https://www.image-map.net/

The NPM is available too: https://www.npmjs.com/package/image-map

The Git Repo fot it: https://github.com/clarketm/image-map

