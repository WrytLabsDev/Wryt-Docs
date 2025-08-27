# Typography & CustomTypography Extensions - extension-typography

The `Typography` and `CustomTypography` extensions for Tiptap add automatic replacements for specific text patterns, transforming them into typographic symbols or special characters. These extensions enhance text input by applying rules for typography and currency symbols, mathematical operators, and more.

## Features

### Typography Extension
The `Typography` extension supports the following replacements:
- **Em Dash (`--`)** → `—`
- **Ellipsis (`...`)** → `…`
- **Double Quotes (`"`)** → `“` or `”`
- **Single Quotes (`'`)** → `‘` or `’`
- **Arrows (`<-`, `->`)** → `←`, `→`
- **Symbols**:
  - Copyright (`(c)`) → `©`
  - Trademark (`(tm)`) → `™`
  - Service Mark (`(sm)`) → `℠`
  - Registered Trademark (`(r)`) → `®`
- **Fractions**:
  - `1/2` → `½`
  - `1/4` → `¼`
  - `3/4` → `¾`
- **Math Operators**:
  - Plus-Minus (`+/-`) → `±`
  - Not Equal (`!=`) → `≠`
  - Multiplication (`*`) → `×`
  - Superscripts (`^2`, `^3`) → `²`, `³`
- **Quotation Marks (`<<`, `>>`)** → `«`, `»`

### CustomTypography Extension
The `CustomTypography` extension supports additional custom symbols:
- **Currency Symbols**:
  - Rupee (`(R)`) → `₹`
  - Dollar (`(USD)`) → `$`
  - British Pound (`(GBP)`) → `£`
  - Australian Dollar (`(AUD)`) → `A$`
  - Euro (`(e)`) → `€`
- **Math Operators**:
  - Triple Equals (`===`) → `≡`
  - Greater/Less Than or Equals (`>=`, `<=`) → `≥`, `≤`
  - Approximation (`(approx)`) → `≈`
  - Pi (`(pi)`) → `π`
  - Not Equal (`!=`) → `≠`
- **Arrows**:
  - Double Arrow (`<==>`) → `⇔`

## Configuration

Both extensions allow customization of specific replacements. You can enable, disable, or override default characters by modifying the options.

Example:
```typescript
import { Typography } from './Typography';
import { CustomTypography } from './CustomTypography';

const typographyExtension = Typography.configure({
    emDash: '⸻', // Custom em dash character
    ellipsis: false, // Disable ellipsis replacement
});
const customTypographyExtension = CustomTypography.configure({
    rupees: false, // Disable Rupee symbol replacement
    pi: 'ππ', // Custom Pi symbol
});
```

## Commands

These extensions do not have commands. Instead, they use text input rules to automatically replace patterns while typing.

## Usage Example

### Integration with Tiptap Editor
```typescript
import { Editor } from '@tiptap/core';
import { Typography } from './Typography';
import { CustomTypography } from './CustomTypography';

const editor = new Editor({
    extensions: [
        Typography,
        CustomTypography,
    ],
    content: `<p>Type (c), --, or (USD) to see replacements.</p>`,
});
```

## HTML Output Example
### Input:
```plaintext
"This is an example..."
"1/2 + 1/4 = 3/4"
"Use ==>, or type (pi)!"
```

### Output:
```html
<p>“This is an example…”</p>
<p>½ + ¼ = ¾</p>
<p>Use ⇔, or type π!</p>
```

## Customization
Each replacement rule can be disabled or customized by passing options during extension configuration.
