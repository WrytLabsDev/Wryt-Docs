# FindAndReplace

The `FindAndReplace` extension for [Tiptap](https://tiptap.dev) enables advanced search and replace functionality. It provides commands to highlight, navigate, and replace occurrences of a search term, with support for case sensitivity and optional regex disabling.

## Overview

This extension allows you to:

- Search text in the editor using a plain string or regex.
- Highlight all search results in the document.
- Navigate between search results.
- Replace a single result or all matches at once.
- Customize styles for highlighted and active results.

## Features

- Inline decorations for all matches
- Scroll-to-view for the active match
- Commands for search, replace, navigation
- Optional case sensitivity and regex disabling
- Configurable highlight classes

## Options

| Name                       | Type         | Default                   | Description                                               |
| -------------------------- | ------------ | ------------------------- | --------------------------------------------------------- |
| `searchTerm`               | `string`     | `""`                      | The current term to search for.                           |
| `replaceTerm`              | `string`     | `""`                      | The current replacement term.                             |
| `results`                  | `Result[]`   | `[]`                      | Internal storage of match positions.                      |
| `currentIndex`             | `number`     | `0`                       | The currently selected match index.                       |
| `searchResultClass`        | `string`     | `"search-result"`         | CSS class applied to all matches.                         |
| `searchResultCurrentClass` | `string`     | `"search-result-current"` | CSS class applied to the active match.                    |
| `caseSensitive`            | `boolean`    | `false`                   | Whether the search is case-sensitive.                     |
| `disableRegex`             | `boolean`    | `true`                    | Whether regex is disabled (true means plain text search). |
| `onChange`                 | `() => void` | `() => {}`                | Optional callback when search state changes.              |

## Commands

### `setSearchTerm(searchTerm: string, caseSensitive: boolean)`
Set the search term and case sensitivity. Triggers a re-scan of the document.

### `setReplaceTerm(replaceTerm: string)`
Set the term to use during replacement operations.

### `replace()`
Replace the currently highlighted search result with the replace term.

### `replaceAll()`
Replace all matched results with the replace term.

### `goToPrevSearchResult()`
Navigate to the previous result in the match list.

### `goToNextSearchResult()`
Navigate to the next result in the match list.

## Usage Example

```ts
import { Editor } from '@tiptap/core'
import StarterKit from '@tiptap/starter-kit'
import { FindAndReplace } from './FindAndReplace' // path to your extension

const editor = new Editor({
  extensions: [
    StarterKit,
    FindAndReplace.configure({
      searchResultClass: 'my-highlight',
      searchResultCurrentClass: 'my-current',
      caseSensitive: false,
      disableRegex: true,
    }),
  ],
})

// Set search and replace terms
editor.commands.findAndReplace.setSearchTerm('example', false)
editor.commands.findAndReplace.setReplaceTerm('demo')

// Replace current or all
editor.commands.findAndReplace.replace()
editor.commands.findAndReplace.replaceAll()

// Navigate results
editor.commands.findAndReplace.goToNextSearchResult()
editor.commands.findAndReplace.goToPrevSearchResult()
```

## Styling Example
```css

.search-result {
  background-color: yellow;
  color: black;
}

.search-result-current {
  background-color: orange;
  border: 1px solid red;
}

```

## HTML Output

The extension uses decorations only and does not affect the underlying HTML content. All search highlights are purely visual and do not alter the document’s structure or saved content.

