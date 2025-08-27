# Details and Summary Extension for Fusion Editor - @fusion/extension-details-summary

## Overview

The `Details` and `Summary` extension provides support for the `<details>` and `<summary>` HTML elements in Fusion Editor. These elements are typically used together to create collapsible content blocks, where the `<summary>` defines the visible heading, and the `<details>` tag contains the content that can be toggled open or closed.

## Features

- **Toggleable Content Blocks:** Allows creating expandable/collapsible sections.
- **Customizable HTML Attributes:** Supports adding custom attributes like `open` for `<details>` and custom `data-*` attributes for `<summary>`.
- **Structured Content:** The `<summary>` is treated as the heading or title, and `<details>` can contain other block-level content.
- **Keyboard Shortcuts and Commands:** Allows you to quickly insert or toggle `<details>` and `<summary>` elements.

## Configuration

### Default Configuration

- **Name:** `details`, `summary`
- **Group:** `block`
- **Content:** 
  - `details` contains a `summary` followed by other block-level content.
  - `summary` contains inline content, acting as a header for the details.
- **Attributes:**
  - `open` (for `<details>`): Indicates whether the details are open or closed.
  - `text` (for `<summary>`): Defines the text of the summary element.
  - Custom attributes for both elements can be added.

### Commands

- **toggleDetails:** Inserts or toggles a `<details>` block element.
  ```typescript
  editor.commands.toggleDetails({ open: true });
  ```

  - **insertDetails:** Inserts a `<details>` block element with or without summary.
  ```typescript
  editor.commands.insertDetails({ open: true, withSummary: true });
  ```

- **setSummary:** Sets the <summary> element inside a <details> block with custom attributes
  ```typescript
  editor.commands.setSummary({ text: 'Summary Text' });
  ```

## Usage
```typescript
const editor = new Editor({
  extensions: [
    Details.configure({
      HTMLAttributes: { class: 'details-class' },
    }),
    Summary.configure({
      HTMLAttributes: { class: 'summary-class' },
    }),
  ],
});
```

## HTML Output
```html
<details class="details-class" open>
  <summary class="summary-class" data-text="More Information">More Information</summary>
  <p>Additional content is displayed here.</p>
</details>
```

## Customization
You can customize the Details and Summary extensions by configuring them with HTML attributes or other options. You can also combine them with other extensions in Fusion Editor to create rich, structured documents.