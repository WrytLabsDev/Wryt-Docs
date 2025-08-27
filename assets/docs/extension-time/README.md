# Time Extension for Fusion Editor - @fusion/extension-time

## Overview

The `@fusion/extension-time` is a Tiptap extension that facilitates the use of the `<time>` HTML element in your content. The `<time>` element represents a specific period in time, such as a date, time of day, or duration, making your content more semantically rich.

## Features

- Support for the `datetime`, `pubdate`, and `title` attributes.
- Allows customization of HTML attributes.
- Provides commands to set, toggle, and unset the `<time>` element.

## Attributes

- **datetime**: A string representing the machine-readable date/time.
- **pubdate**: A boolean indicating if the date represents the publication date.
- **title**: A string providing additional information about the time element.

## Commands

- **`setTime`**: Inserts a `<time>` element with specified attributes.
- **`toggleTime`**: Toggles the `<time>` element on the selected text.
- **`unsetTime`**: Removes the `<time>` element from the selected text.

## Configuration

```typescript
import { Time } from '@fusion/extension-time';

const editor = new Editor({
  extensions: [
    Time.configure({
      HTMLAttributes: {
        class: 'custom-time-class',
      },
    }),
  ],
});
```

## Usage Example / Customization (Optional)

You can customize the datetime, pubdate, and title attributes using the setTime command. For instance:

```typescript
editor.commands.setTime({
  datetime: '2024-08-30',
  pubdate: true,
  title: 'Event Date',
});
```

## HTML Output Example

```html
<p>
  The Cure will be celebrating their 40th anniversary on <time datetime="2018-07-07">July 7</time> in London's Hyde
  Park.
</p>

<p>
  The concert starts at <time datetime="20:00">20:00</time> and you'll be able to enjoy the band for at least
  <time datetime="PT2H30M">2h 30m</time>.
</p>
```