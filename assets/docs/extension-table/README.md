# Table Extension

## Overview
The TableView extension in Tiptap provides a flexible and customizable way to handle tables in your Tiptap editor. This extension enhances the native ProseMirror table functionality with additional options for controlling the behavior and appearance of tables.

## Features
- Customizable table structure and formatting.
- Built-in commands for table manipulation (e.g., adding rows, columns, and merging cells).
- Easy integration with Tiptap's core functionality.
- Support for table customization, including class names and attributes.

## Commands

### `addTable`
Adds a new table with a given number of rows and columns.

```typescript
editor.chain().focus().addTable({ rows: 3, cols: 3 }).run();
```

### `addColumnBefore`
Adds a new column before the currently selected column.

```typescript
editor.chain().focus().addColumnBefore().run();
```

### `addColumnAfter`
Adds a new column after the currently selected column.

```typescript
editor.chain().focus().addColumnAfter().run();
```

### `deleteColumn`
Deletes the currently selected column.

```typescript
editor.chain().focus().deleteColumn().run();
```

### `addRowBefore`
Adds a new row before the currently selected row.

```typescript
editor.chain().focus().addRowBefore().run();
```

### `addRowAfter`
Adds a new row after the currently selected row.

```typescript
editor.chain().focus().addRowAfter().run();
```

### `deleteRow`
Deletes the currently selected row.

```typescript
editor.chain().focus().deleteRow().run();
```

### `mergeCells`
Merges the selected cells.

```typescript
editor.chain().focus().mergeCells().run();
```

### `splitCell`
Splits the currently selected merged cell.

```typescript
editor.chain().focus().splitCell().run();
```

### `toggleHeaderRow`
Toggles the header row for the table.

```typescript
editor.chain().focus().toggleHeaderRow().run();
```

### `toggleHeaderColumn`
Toggles the header column for the table.

```typescript
editor.chain().focus().toggleHeaderColumn().run();
```

### `toggleCellMerge`
Toggles the merging state for the selected cells.

```typescript
editor.chain().focus().toggleCellMerge().run();
```

## Keyboard Shortcuts
- **Tab**: Move to the next cell. If it's the last cell, add a new row and move to the next cell.
- **Shift-Tab**: Move to the previous cell.
- **Backspace**: Delete the table when all cells are selected.
- **Mod-Backspace**: Delete the table when all cells are selected.
- **Delete**: Delete the table when all cells are selected.
- **Mod-Delete**: Delete the table when all cells are selected.

## Usage Example
```typescript
import { Editor } from '@tiptap/core';
import { TableView } from './TableView';

const editor = new Editor({
  extensions: [
    Table.configure({
      resizable: true,
    }),
    TableRow,
    TableHeader,
    TableCell,
  ],
});

editor.commands.addTable({ rows: 3, cols: 3 });
```

## HTML Output Example
```html
<table>
  <thead>
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
      <th>Header 3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Row 1, Cell 1</td>
      <td>Row 1, Cell 2</td>
      <td>Row 1, Cell 3</td>
    </tr>
    <tr>
      <td>Row 2, Cell 1</td>
      <td>Row 2, Cell 2</td>
      <td>Row 2, Cell 3</td>
    </tr>
  </tbody>
</table>
```