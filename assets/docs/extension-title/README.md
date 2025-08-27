# Title Extension for Fusion Editor - @fusion/extension-title

## Overview
The Title extension allows you to insert `<title>` elements, which define the title of the document, typically displayed in the browser's title bar or tab.

## Features
- Supports the basic functionality of the `<title>` element.
- Allows defining the document's title within the editor.

## Attributes
- **text**: The text content that will be displayed as the title.

## Commands
- **setTitle**: Inserts or updates a `<title>` element.
- **unsetTitle**: Removes the currently selected `<title>` element.

## Configuration
The extension can be configured with the following options:
- **HTMLAttributes**: An object of HTML attributes that will be applied to the `<title>` element.

## Usage Example
```javascript
editor.commands.setTitle({ text: 'My Document Title' });
```

## HTML Output Example

```html
<title>My Document Title</title>
```