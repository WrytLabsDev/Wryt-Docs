
# History Extension for Fusion Editor - @fusion/extension-history

## Overview

The `History` extension provides undo and redo functionality within the Tiptap editor. It integrates with ProseMirror's built-in history handling and allows you to manage the depth of undoable steps and the time delay for creating new history groups.

**Important**: If you're using the `@tiptap/extension-collaboration` package, you should not include this extension as it conflicts with the collaboration extension, which has its own history implementation.

## Features

- Undo recent changes.
- Redo reverted changes.
- Configurable history depth and group delay.
- Keyboard shortcuts for undo and redo, including support for Russian keyboard layouts.

## Attributes

| Name            | Type    | Default | Description                                              |
|-----------------|---------|---------|----------------------------------------------------------|
| `depth`         | number  | `100`   | The number of history events to store.                   |
| `newGroupDelay` | number  | `500`   | The time in milliseconds after which a new change group is created. |

## Commands

| Command  | Description               | Example                     |
|----------|---------------------------|-----------------------------|
| `undo`   | Undo recent changes        | `editor.commands.undo()`     |
| `redo`   | Reapply reverted changes   | `editor.commands.redo()`     |

## Configuration

The `History` extension accepts the following options to configure its behavior:

```typescript
History.create({
  depth: 50, // Custom history depth
  newGroupDelay: 1000, // Delay for grouping changes
})
```

## Keyboard Shortcuts

| Shortcut          | Action             |
|-------------------|--------------------|
| `Mod-z`           | Undo               |
| `Shift-Mod-z`     | Redo               |
| `Mod-y`           | Redo (alternative) |
| `Mod-я`           | Undo (Russian)     |
| `Shift-Mod-я`     | Redo (Russian)     |

## Usage Example

```typescript
import { Editor } from '@tiptap/core'
import { History } from './extensions/history'

const editor = new Editor({
  extensions: [
    History.configure({
      depth: 50,           // Custom history depth
      newGroupDelay: 1000, // Custom group delay for new actions
    }),
  ],
})
```