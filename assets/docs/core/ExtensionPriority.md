# Understanding Priority in Fusion Editor Extensions

## Overview

In Fusion, the `priority` setting for extensions plays a crucial role in determining how competing extensions or node types are resolved. This document provides an overview of how the priority value affects extension behavior and helps manage conflicts within the editor.

## Priority Value

The `priority` value in Tiptap extensions affects how conflicts are managed and how different extensions interact with each other. It helps to resolve which extension should take precedence when multiple extensions might influence the same part of the editor.

### Default Values

- **Default Behavior:** If you do not explicitly set a priority value, Fusion uses default values. These defaults may not always align with your specific needs or use cases.
- **Control and Precision:** By setting a priority value, you gain greater control over the behavior of your extensions, ensuring that they function as intended in your editor setup.

### Higher Priority Values

- **Precedence:** Extensions with higher priority values (e.g., `1000`) are generally favored over those with lower values. This means that in scenarios where multiple extensions could potentially handle the same content or behavior, the extension with the higher priority will be given precedence.
- **Consistency:** Setting a high priority value is important for maintaining consistent behavior, especially when dealing with overlapping functionalities or content types.

### Use Case

In the context of the `Paragraph` extension, setting a priority value of `1000` ensures that this extension is given precedence in scenarios where it might conflict with other block-level extensions. This helps to maintain consistent behavior in the editor, ensuring that paragraphs are handled correctly and that any conflicts with other extensions are minimized.

## Conclusion

Understanding and setting the priority value for your extensions in Fusion allows you to manage conflicts and ensure that your editor behaves consistently and predictably. By assigning appropriate priority values, you can control how different extensions interact and how content is handled within the editor.

For more information on managing extensions and configuring priorities, refer to the [Fusion Documentation](https://fusion.dev/).
