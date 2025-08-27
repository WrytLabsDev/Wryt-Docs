# Gapcursor Extension - @fusion/extension-gapcursor

The `Gapcursor` extension enables a gap cursor feature within the editor, allowing a cursor to appear in places where there is no content, such as between nodes. This extension adds flexibility in navigating empty spaces within the document.

## Overview

This extension integrates the ProseMirror gap cursor into a Tiptap editor. A gap cursor is a visual indicator that appears between nodes when there is no content, allowing users to select, insert, or interact with otherwise inaccessible areas.

## Features

- Displays a gap cursor at empty areas between nodes, improving navigation.
- Customizable with CSS to fit light and dark themes.

## Node Configuration

In the Tiptap configuration, you can specify whether the gap cursor is allowed at certain positions using the `allowGapCursor` setting. This setting supports:
- `true`: Always show the gap cursor.
- `false`: Disable the gap cursor.
- A function that returns a boolean, providing conditional control over where the gap cursor appears.

## Installation

To install, import the `Gapcursor` extension:

```typescript
import { Gapcursor } from 'path/to/gapcursor-extension';
```

## Usage

- Include the Gapcursor extension in your editor's extensions:

```typescript
import { Gapcursor } from 'path/to/gapcursor-extension';

const editor = new Editor({
    extensions: [
        Gapcursor,
        // other extensions
    ],
});
```

## Configuration Options

```typescript
Gapcursor.configure({
    allowGapCursor: (context) => {
        return context.name !== 'image'; // Allow gap cursor except near image nodes
    },
});

Or

// Each extension has to allowGapCursor: true

```


## Styling

```css

/* Base styling for the ProseMirror gap cursor */
.ProseMirror-gapcursor {
    display: none;
    pointer-events: none;
    position: absolute;
    width: 2px;
    background-color: rgba(0, 0, 0, 0.5);
    margin: 0;
    animation: ProseMirror-cursor-blink 1s steps(2, start) infinite;
}

.ProseMirror-focused .ProseMirror-gapcursor {
    display: block;
}

.ProseMirror .ProseMirror-gapcursor {
    margin-left: auto;
    margin-right: auto;
    width: 1px;
    max-width: 40rem;
    height: 1.2em;
}

.ProseMirror-gapcursor:after {
    content: "";
    display: block;
    position: absolute;
    top: -2px;
    width: 18px;
    border-top: 1px solid rgba(0, 0, 0, 0.4);
    margin: 0 auto;
    animation: ProseMirror-cursor-blink 1s steps(2, start) infinite;
}

:is(.dark .ProseMirror-gapcursor) {
    background-color: rgba(255, 255, 255, 0.6);
}

:is(.dark .ProseMirror-gapcursor):after {
    border-top-color: rgba(255, 255, 255, 0.4);
}

@keyframes ProseMirror-cursor-blink {
    0% {
        opacity: 1;
    }

    50% {
        opacity: 0;
    }

    100% {
        opacity: 1;
    }
}

```