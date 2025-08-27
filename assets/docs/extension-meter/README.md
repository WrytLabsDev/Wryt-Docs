# `<meter>` Extension for Fusion Editor - @fusion/extension-meter

## Overview

The `<meter>` extension allows you to display a scalar measurement within a known range. It is commonly used to represent values such as disk usage, the relevance of a query result, or a voting score.

## Features

- **Semantic Measurement:** Provides a semantic representation of a measurement within a range.
- **Customizable Attributes:** Supports attributes like `min`, `max`, `low`, `high`, `optimum`, and `value` to configure the meter display.
- **Inline Content:** The `<meter>` tag is treated as inline content, allowing it to be embedded in a block of text.

## Attributes

- **HTML Attributes:** Customize the HTML attributes of the `<meter>` element using the `HTMLAttributes` option.

  - **`min`**: The minimum value of the range.
  - **`max`**: The maximum value of the range.
  - **`low`**: The lower bound of the "low" range.
  - **`high`**: The lower bound of the "high" range.
  - **`optimum`**: The optimum value in the range.
  - **`value`**: The current value of the meter.

## Commands

- **insertMeter:** Inserts a `<meter>` element into the document with optional attributes.

## Configuration

### Default Configuration

- **Name:** `meter`
- **Group:** The extension is applied as an inline element.
- **Content:** The extension can contain inline content.
- **Parse HTML:** Recognizes `<meter>` tags when parsing HTML input.
- **Render HTML:** Outputs `<meter>` tags with any additional HTML attributes.

## Keyboard Shortcuts

- **None:** Currently, no default keyboard shortcuts are defined for this extension.

## Customization

You can customize the `<meter>` extension by passing in attributes like `value`, `min`, and `max` through the `insertMeter` command.

## Usage Example

```typescript
import { MeterExtension } from '@fusion/extension-meter';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [MeterExtension, /* other extensions */],
});

// Insert a <meter> element
editor.commands.insertMeter({
  attrs: { value: 0.7, min: 0, max: 1, optimum: 0.9 },
  content: [{ type: 'text', text: '70%' }],
});
```

## HTML Output Example
```html
<p>The relevance score is <meter value="0.7" min="0" max="1" optimum="0.9">70%</meter>.</p>
```