# Break Extension for Fusion Editor - @fusion/extension-break

## Overview
The Break extension provides support for inserting line breaks (<br> elements) in Fusion Editor. This extension allows users to add hard breaks in their content while optionally preserving any active text formatting marks.

This extension is especially useful in content creation scenarios where explicit line breaks are necessary, such as poetry, addresses...etc.

## Features
- **Line Break Support:** Enables the insertion of <br> elements to create hard line breaks within content.
- **Control Over Marks:** Provides an option to keep or discard formatting marks when a line break is inserted.
- **Customizable HTML Attributes:** Supports customization of HTML attributes for the <br> tag.
- **Keyboard Shortcuts:** Common shortcuts like Mod-Enter and Shift-Enter are provided for inserting line breaks.

## Configuration
### Default Configuration
- **Name:** break
- **Group:** inline
- **Selectable:** false
- **Atom:** true
- **Inline:** true
- **Keep Marks:** true (Default behavior is to retain formatting marks after a line break.)
- **Parse HTML:** Recognizes the <br> tag when parsing HTML input.
- **Render HTML:** Outputs a <br> tag with any additional HTML attributes.
- **Render Text:** Returns \n to indicate a line break in plain text

## Commands

- **setBreak:** Inserts a line break (`<br>` tag) into the content.

```typescript
editor.commands.setBreak();
```

## Keyboard Shortcuts

- **Mod-Enter:** Inserts a line break.
- **Shift-Enter:** Inserts a line break.

## Customization
### Options

- **keepMarks:** (boolean) Controls whether text formatting marks (like bold or italic) are kept after the break. Defaults to true.
```typescript
    Break.configure({ keepMarks: false });
```

- **HTMLAttributes:** (Record<string, any>) Allows customization of the HTML attributes for the <br> element.
```typescript
    Break.configure({ 
        HTMLAttributes: { class: 'my-custom-class' }
    });
```

## Example Usage

```typescript

import { Break } from '@fusion/extension-break';

// Add the extension to your editor setup
const editor = new Editor({
  extensions: [
    Break.configure({ keepMarks: true }),
    /* other extensions */
  ],
});

```

## HTML Output

```html

<p>
  O’er all the hilltops<br />
  Is quiet now,<br />
  In all the treetops<br />
  Hearest thou<br />
  Hardly a breath;<br />
  The birds are asleep in the trees:<br />
  Wait, soon like these<br />
  Thou too shalt rest.
</p>
```


