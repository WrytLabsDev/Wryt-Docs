# List Extensions for Fusion - @fusion/extension-list

This package includes multiple Fusion extensions for working with lists: Bullet List, Ordered List, List Item, Task List, and List Keymap. These extensions provide various list types and customization options for your editor.

## Overview

The extensions included in this package are:

- **BulletList**: Create and toggle bullet (unordered) lists.
- **OrderedList**: Create and toggle ordered (numbered) lists.
- **ListItem**: Represent individual list items in bullet or ordered lists.
- **TaskList**: Create and toggle task lists with checkboxes.
- **ListKeymap**: Customize key behavior for lists, enhancing the handling of backspace and delete keys.

## Features

### Bullet List
- Toggle bullet lists using dashes or asterisks.
- Keep marks and attributes when splitting list items.
- Provides keyboard shortcut: `Mod-Shift-8`.

### Ordered List
- Toggle ordered lists using number followed by a dot.
- Keep marks and attributes when splitting list items.
- Provides keyboard shortcut: `Mod-Shift-7`.
- Supports start attributes for ordered lists.

### List Item
- Supports nesting of paragraphs and other block elements inside list items.
- Provides shortcuts for `Enter`, `Tab`, and `Shift-Tab` for list item manipulation.

### Task List
- Toggle task lists with customizable task items.
- Provides keyboard shortcut: `Mod-Shift-9`.

### List Keymap
- Custom keymap for handling backspace and delete behavior in lists.
- Prevents ProseMirror’s default behavior of joining list items into paragraphs.

## Commands

### Bullet List Commands
- Toggle bullet list for the current selection.

```typescript
toggleBulletList(): void
```

### Ordered List Commands
- Toggle ordered list for the current selection.

```typescript
toggleOrderedList(): void
```

### Task List Commands
- Toggle task list for the current selection.

```typescript
toggleTaskList(): void
```

## Configuration

```typescript
import { BulletList, OrderedList, ListItem, TaskList, TaskItem, ListKeymap } from '@fusion/extension-list'

const editor = new Editor({
  extensions: [
    BulletList,
    OrderedList,
    ListItem,
    TaskList,
    ListKeymap,
  ],
})
```

#### BulletList
```typescript
{
  itemTypeName: 'listItem',   // Node name for list items
  HTMLAttributes: {},         // HTML attributes for the bullet list
  keepMarks: false,           // Whether to keep marks when splitting list items
  keepAttributes: false,      // Whether to keep attributes when splitting list items
}
```

#### OrderedList
```typescript
{
  itemTypeName: 'listItem',   // Node name for list items
  HTMLAttributes: {},         // HTML attributes for the ordered list
  keepMarks: false,           // Whether to keep marks when splitting list items
  keepAttributes: false,      // Whether to keep attributes when splitting list items
  start: 1,                   // Starting number for ordered list
  type: undefined,            // Type of ordered list (e.g., '1', 'A', 'a', 'I', 'i')
}
```

#### TaskList
```typescript
{
  itemTypeName: 'taskItem',   // Node name for task items
  HTMLAttributes: {},         // HTML attributes for the task list
}
```

#### ListItem
```typescript
{
  HTMLAttributes: {},         // HTML attributes for the list item
  bulletListTypeName: 'bulletList', // Node type for bullet lists
  orderedListTypeName: 'orderedList' // Node type for ordered lists
}
```

#### ListKeymap
```typescript
{
  listTypes: [
    {
      itemName: 'listItem',    // Node type for list items
      wrapperNames: ['bulletList', 'orderedList'], // Wrapper types for bullet and ordered lists
    },
    {
      itemName: 'taskItem',    // Node type for task items
      wrapperNames: ['taskList'], // Wrapper types for task lists
    },
  ]
}
```

## Keyboard Shortcuts

- **BulletList:** Mod-Shift-8 to toggle bullet list.
- **OrderedList:** Mod-Shift-7 to toggle ordered list.
- **TaskList:** Mod-Shift-9 to toggle task list.
- **Enter:** Split the current list item.
- **Tab:** Sink the current list item (indent).
- **Shift-Tab:** Lift the current list item (outdent).


## HTML Output Example

## Bullet List
```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

## Ordered List
```html
<ol start="1">
  <li>First item</li>
  <li>Second item</li>
</ol>
```

## Task List
```html
<ul data-type="taskList">
  <li data-type="taskItem" data-checked="true">flour</li>
  <li data-type="taskItem" data-checked="true">baking powder</li>
  <li data-type="taskItem" data-checked="true">salt</li>
  <li data-type="taskItem" data-checked="false">sugar</li>
  <li data-type="taskItem" data-checked="false">milk</li>
  <li data-type="taskItem" data-checked="false">eggs</li>
  <li data-type="taskItem" data-checked="false">butter</li>
</ul>
```

