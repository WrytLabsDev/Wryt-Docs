# Output Extension for Fusion Editor - @fusion/extension-output

## Overview

The `Output` extension allows you to include the `<output>` HTML element in your Fusion Editor. The `<output>` element is typically used to display the result of a calculation or user action, often in association with `<input>` elements.

## Features

- **Display Calculation Results:** Use the `<output>` element to display dynamic results.
- **Associations:** The `for` attribute allows you to associate the output with one or more input elements.
- **Name Attribute:** The `name` attribute allows the element to be identified within forms.

## Commands

- **setOutput:** Adds an output element to the editor with optional attributes.
```typescript
editor.commands.setOutput({ for: 'inputId', name: 'result' });
```

## Attributes
- **for:** The for attribute links the output element to one or more form elements
- **name:** The name attribute represents the name of the output element, which is submitted with the form.

## Usage Example
```typescript
import { Output } from '@fusion/extension-output';

const editor = new Editor({
  extensions: [
    Output.configure({
      HTMLAttributes: {
        class: 'custom-output',
      },
    }),
    // other extensions
  ],
});

editor.commands.setOutput({ for: 'inputId', name: 'calculationResult' });

```

## HTML Output Example

```html
<form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
  <input type="range" id="a" value="50"> +
  <input type="number" id="b" value="50">
  <output name="result" for="a b">100</output>
</form>

```