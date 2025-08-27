# Audio, Video, and Picture Extensions for Fusion Editor - @fusion/extension-media

## Overview

#### Audio
The Audio extension allows for the embedding and control of audio elements within the Fusion Editor. It supports both block-level and inline audio elements, accommodating various sources and fallback content.

#### Video
The Video extension allows for the embedding and control of video elements within the Fusion Editor. Like the Audio extension, it supports block-level and inline video elements and handles multiple sources.

#### Picture
The Picture extension enables the use of the <picture> element in the Fusion Editor, which is essential for responsive images. It allows specifying multiple image sources and formats to adapt to different screen sizes or resolutions.


## Features

- Block and Inline Audio Support: Audio, Video and Picture can be rendered as either block-level or inline elements based on context.
- Multiple Sources Support: Handles multiple `<source>` elements within the `<audio>`, `<video>`, `<picture>` tags.
- Fallback Content: Allows the inclusion of fallback text within the `<audio>`, `<video>`, `<picture>` element for unsupported browsers.
- Responsive Images: Supports the <picture> element to provide multiple image sources.
- Source and Image Handling: Manages <source> elements within <picture> and the fallback <img> element.

## Audio Example

```typescript
import { Audio, InlineAudio, Source } from '@fusion/extension-media';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Audio, InlineAudio, Source /* other extensions */],
});

```

## HTML Output

```html
<audio controls src="https://interactive-examples.mdn.mozilla.net/media/cc0-audio/t-rex-roar.mp3"></audio>

<p>Audio inside paragraph tag <audio controls src="https://interactive-examples.mdn.mozilla.net/media/cc0-audio/t-rex-roar.mp3"></audio>
  <a href="https://interactive-examples.mdn.mozilla.net/media/cc0-audio/t-rex-roar.mp3"> Download audio </a>
  </p>

<audio controls>
  <source src="https://www.w3schools.com/tags/horse.ogg" type="audio/ogg">
  <source src="https://www.w3schools.com/tags/horse.mp3" type="audio/mpeg">
  Your browser does not support the audio tag.
</audio>

```

## Video Example

```typescript
import { Video, InlineVideo, Source } from '@fusion/extension-media';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Video, InlineVideo, Source /* other extensions */],
});

```

## HTML Output

```html

<p> 
    The controls attribute adds video controls, 
<video controls src="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/friday.mp4">
  <track default kind="captions" src="https://interactive-examples.mdn.mozilla.net/media/examples/friday.vtt" />
</video>
like play, pause, and volume.
</p>

<video controls width="250">
  <source src="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm" type="video/webm" />

  <source src="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4" type="video/mp4" />

  Download the
  <a href="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm">WEBM</a>
  or
  <a href="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4">MP4</a>
  video.
</video>

<video controls src="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/friday.mp4">
  <track default kind="captions" src="https://interactive-examples.mdn.mozilla.net/media/examples/friday.vtt" />
</video>
```

## Picture Example

```typescript
import { Picture, InlinePicture, Source } from '@fusion/extension-media';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Picture, InlinePicture, Source /* other extensions */],
});

```

## HTML Output

```html
<picture>
  <source srcset="https://interactive-examples.mdn.mozilla.net/media/cc0-images/surfer-240-200.jpg" media="(orientation: portrait)" />
  <img src="https://interactive-examples.mdn.mozilla.net/media/cc0-images/painted-hand-298-332.jpg" alt="" />
</picture>

<p>
  <picture>
    <source srcset="https://interactive-examples.mdn.mozilla.net/media/cc0-images/surfer-240-200.jpg" media="(orientation: portrait)" />
    <img src="https://interactive-examples.mdn.mozilla.net/media/cc0-images/painted-hand-298-332.jpg" alt="" />
  </picture>
</p>
```