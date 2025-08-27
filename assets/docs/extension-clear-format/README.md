# ClearFormat Extension for Fusion Editor - `@fusion/extension-clear-format`

## Overview

The ClearFormat extension provides a unified command for removing all text formatting and optionally clearing HTML node attributes in the Fusion Editor. This includes removing all marks (e.g., bold, italic), block formatting (e.g., headings, lists), and optionally cleaning node attributes such as `style`, `class`, and `data-*`.

## Features

* **Clear All Marks and Nodes:** Removes inline formatting (marks) and block-level structure (nodes).
* **Optional Attribute Cleaning:** Can be configured to remove unwanted node attributes like `style`, `class`, or `data-*`.
* **Non-breaking Space Normalization:** Includes a helper command to replace non-breaking spaces (`&nbsp;`) with regular spaces.
* **Developer Configurable:** Developers can customize which attributes to strip from nodes.

## Configuration

#### Default Configuration

* Name: `clearFormat`
* Group: `utility`
* Default Behavior: Only clears formatting (`clearNodes()` + `unsetAllMarks()`); does not remove any node attributes unless configured.

#### Available Options

| Option                 | Type       | Default     | Description                                           |
| ---------------------- | ---------- | ----------- | ----------------------------------------------------- |
| `attributesToRemove`   | `string[]` | `undefined` | List of node attributes to remove (e.g., `['style']`) |
| `removeDataAttributes` | `boolean`  | `false`     | Whether to remove all `data-*` attributes from nodes  |

## Commands

* **clearFormat:**

  * Removes all marks and block-level node formatting.
  * Optionally removes node attributes if configured.

* **clearNonBreakingSpace:**

  * Replaces non-breaking spaces (`\u00A0`) with regular spaces (`' '`) in the selected range.

## Example

```ts
import { ClearFormat } from '@fusion/extension-clear-format';

// Register the extension with optional configuration
const editor = new Editor({
  extensions: [
    ClearFormat.configure({
      attributesToRemove: ['style', 'class'],
      removeDataAttributes: true,
    }),
    // other extensions...
  ],
});

// Usage
editor.commands.clearFormat();
editor.commands.clearNonBreakingSpace();
```

## HTML Output

```html
<!-- Before -->
<p style="color:red" class="note">Some <strong>formatted</strong> text&nbsp;here.</p>
```

<!-- After clearFormat -->
<p>Some formatted text here.</p>
```
