# Progress Extension for Fusion Editor - @fusion/extension-progress

## Overview

The `Progress` extension allows you to include a progress bar within the Fusion Editor. This is particularly useful for visually indicating the completion status of a task or the progress of a download.

## Features

- **Block Node:** Renders the `<progress>` element as a block-level node.
- **Command Integration:** Provides a command to set the `<progress>` node with configurable attributes like `value` and `max`.
- **Custom HTML Attributes:** Allows customization of the HTML attributes for the `<progress>` element.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<progress>` element using the `HTMLAttributes` option.
- **Value:** Specifies how much of the task has been completed.
- **Max:** Specifies the total amount of work to complete the task.

## Commands

- **setProgress:** Inserts the `<progress>` node with optional `value` and `max` attributes.
```typescript
editor.commands.setProgress({ value: 0.5, max: 1.0 });
```

## Configuration

### Default Configuration

- **Name:** progress
- **Block:** The extension is applied as a block node.
- **Parse HTML:** Recognizes <progress> tags when parsing HTML input.
- **Render HTML:** Outputs <progress> tags with any additional HTML attributes.

## Usage Example

```typescript
import { Progress } from '@fusion/extension-progress';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [Progress, /* other extensions */],
});
```

## HTML Output Example
```html
<p>Task progress: <progress value="0.5" max="1.0"></progress></p>
```

