# CharacterCount Extension - extension-character-count

The **CharacterCount** extension for Tiptap allows you to monitor and control the number of characters and words in a document. It provides configurable options such as setting limits, determining calculation modes, and defining custom counter functions for characters and words.

---

## Features

- **Character Counting**: Count characters using either `textContent` or `nodeSize`.
- **Word Counting**: Calculate the number of words in the document.
- **Character Limits**: Define a maximum character count and trim the content if it exceeds the limit.
- **Custom Counter Functions**: Use your own logic for character or word counting.
- **Configurable Modes**: Choose between `textSize` or `nodeSize` for size calculations.
- **Automatic Trimming**: Removes excess content when the document exceeds the character limit.

---

## Attributes

| Attribute    | Type                   | Default    | Description                                       |
|--------------|------------------------|------------|---------------------------------------------------|
| `limit`      | `number | null`        | `null`     | Maximum allowed characters.                      |
| `mode`       | `'textSize' | 'nodeSize'` | `'textSize'` | Defines the counting method.                     |
| `textCounter`| `(text: string) => number` | `text.length` | Function to calculate character count.           |
| `wordCounter`| `(text: string) => number` | `split(' ').filter(...).length` | Function to calculate word count.               |

---

## Storage

| Method       | Parameters                         | Description                                       |
|--------------|------------------------------------|---------------------------------------------------|
| `characters` | `{ node, mode }`                  | Gets the number of characters in a node or document. |
| `words`      | `{ node }`                        | Gets the number of words in a node or document.  |

---

## Commands

No explicit commands are exposed by this extension. Its functionality is designed to work seamlessly in the background.

---

## Configuration

### Default Options
```typescript
CharacterCount.create({
  limit: null,
  mode: 'textSize',
  textCounter: text => text.length,
  wordCounter: text => text.split(' ').filter(word => word !== '').length,
});
```

### Example Usage
```typescript
const characterCount = CharacterCount.create({
  limit: 180, // Set a character limit
  mode: 'textSize', // Use text content for size calculation
  textCounter: text => [...new Intl.Segmenter().segment(text)].length, // Custom character counter
  wordCounter: text => text.split(/\s+/).filter(word => word !== '').length, // Custom word counter
});
```

---

## Behavior

- **Initial Content Validation**: Automatically trims content if it exceeds the character limit when the document is first loaded.
- **Transaction Filtering**: Blocks transactions that would exceed the character limit unless they result in content reduction.

---

## Example HTML Output

```html
<p>This is an example paragraph with a maximum character limit.</p>
```

---

## Notes

- **Pasting Content**: When content is pasted, the extension ensures that it stays within the character limit by trimming excess characters.
- **Transaction Safety**: Handles transactions safely without causing inconsistencies in the document structure.

Feel free to adjust the extension to suit your needs. If you encounter any issues, review the `filterTransaction` logic or adjust the default counters.

