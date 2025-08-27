# Abbr Extension - extension-abbr

The `Abbr` extension for Fusion adds support for the `<abbr>` HTML tag, enabling you to define abbreviations in your content with a `title` attribute that provides additional context. This extension is useful for enhancing the readability and accessibility of content where abbreviations or acronyms are used.

## Features

- **Abbreviation Mark:** Adds the `<abbr>` tag, allowing you to wrap text with an abbreviation and a `title` attribute.
- **Title Attribute:** Provides a `title` attribute to describe the abbreviation, which can be displayed as a tooltip when the user hovers over the abbreviation.
- **Commands:** Includes commands to set and unset the abbreviation mark, providing flexibility in content creation.
- **Keyboard Shortcuts:** Supports a keyboard shortcut for toggling abbreviations, making it easier to apply this formatting quickly.

## Installation

To integrate the `Abbr` extension into your Fusion editor, you'll need to install the core Fusion library. If you haven’t already done so, you can install it using npm:

```bash
npm install @fusion/core
```

## Set Abbreviation

This command wraps the selected text in an `<abbr>` tag with the specified title attribute.

### Example usage

```typescript
editor.commands.setAbbr({ title: 'Hypertext Markup Language' });
```

### Unset Abbreviation:

This command removes the abbreviation mark from the selected text.

```typescript
editor.commands.unsetAbbr();
```

## Example

Here’s an example of what the HTML output might look like when using the [Abbr](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/abbr) extension:

```html
<p>
  This is an example of an
  <abbr title="Hypertext Markup Language">HTML</abbr>
  abbreviation.
</p>
```

