# Address Extension - extension-address

## Overview
The Address extension for Fusion Editor introduces the ability to use the `<address>` HTML element within your editor. The `<address>` element indicates that the enclosed HTML provides contact information for a person, people, or an organization. This extension is built to conform to HTML5 standards and best practices.

## Installation
To use the Address extension in your editor, you can import and include it in your Tiptap extensions setup.

```javascript
import { Address } from './extensions/Address';

const editor = new Editor({
  extensions: [
    // other extensions
    Address,
  ],
});
```

## HTML Output

This extension will render content within an `<address>` element, with support for custom attributes like class and id.

```html
<address class="contact-info" id="company-address">
  1234 Elm Street, Springfield, USA
</address>
```

## Commands

### SetAddress

```typescript
editor.commands.setAddress({
  class: 'contact-info',
  id: 'company-address',
});
```

### Usage Notes
- The `<address>` element should not be used for arbitrary addresses (e.g., home addresses), but specifically for contact information.

- It should not be used inside an `<article>` or `<section>` element if the contact information is not relevant to that section.
