# `<dl>`, `<dt>`, and `<dd>` Extension

## Overview
This extension provides support for creating and manipulating HTML description lists (`<dl>`), terms (`<dt>`), and descriptions (`<dd>`) in the Tiptap editor. 

A description list is typically used to define terms and their associated descriptions or values.

## Features
- Support for `<dl>`, `<dt>`, and `<dd>` elements.
- Ensures proper nesting of terms (`<dt>`) and descriptions (`<dd>`) within a description list (`<dl>`).

## Commands
- **Insert Description List (<dl>):** Use the command `setDl` to add a new description list.
- **Insert Term (<dt>):** Use the command `setDt` to add a new term inside a description list.
- **Insert Description (<dd>):** Use the command `setDd` to add a new description associated with a term.

```typescript
editor.commands.setDl();
editor.commands.setDt();
editor.commands.setDd();
```

## Configuration
```typescript
import { Cite } from '@fusion/extension-desc-list';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Dl,
    Dt,
    Dd,
    /* other extensions */
  ],
});
```

## Usage Example
```typescript
import { Dl, Dt, Dd } from './your-extension-path';

const editor = new Editor({
  extensions: [
    Dl,
    Dt,
    Dd,
    // other extensions
  ],
});
```

## Example HTML Output
```html
<dl>
  <dt>HTML</dt>
  <dd>A markup language for creating web pages.</dd>
  <dt>CSS</dt>
  <dd>A style sheet language for designing web pages.</dd>
</dl>
```

