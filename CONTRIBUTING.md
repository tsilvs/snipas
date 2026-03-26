# Contributing to Snipas

Thank you for your interest in contributing to Snipas! This document provides guidelines and instructions for contributing.

## How to Contribute

### Adding New Snippets

1. Fork the repository
2. Add or modify snippets in the `snippets/` directory
3. Follow the existing format and naming conventions
4. Test your snippets in Zed
5. Submit a pull request

### Snippet Guidelines

#### File Naming

- Use lowercase filenames matching the language scope
- Use `.json` extension
- For multi-word languages, use spaces (e.g., `shell script.json`)
- Refer to Zed's scope naming conventions

#### Snippet Format

Follow this structure for all snippets:

```json
{
  "Snippet Name": {
    "prefix": "trigger",
    "body": [
      "line 1",
      "line 2 with ${1:placeholder}"
    ],
    "description": "Optional description"
  }
}
```

#### Best Practices

1. **Prefix Naming**: Use short, memorable prefixes
   - Use colons for namespacing (e.g., `ascii:block`)
   - Use special characters for quick access (e.g., `!n` for note)

2. **Placeholders**: Use meaningful defaults
   - `$1`, `$2` for tab stops
   - `${1:defaultValue}` for placeholders with defaults
   - `$0` for final cursor position

3. **Descriptions**: Write clear, concise descriptions
   - Explain what the snippet does
   - Mention any important behavior

4. **Body Formatting**: Maintain consistent indentation
   - Use tabs for indentation in the snippet body
   - Keep lines at a reasonable length

5. **Escaping**: Remember to escape `$` symbols
   - Use `\\$var` for literal dollar signs
   - Escape backslashes when needed

### Testing Snippets

Before submitting:

1. Copy your snippet file to `~/.config/zed/snippets/`
2. Restart Zed or reload the window
3. Test the snippet trigger and expansion
4. Verify all placeholders work correctly
5. Check that indentation is correct

### Pull Request Process

1. Update the README.md if adding new snippet categories
2. Ensure your snippets follow the guidelines above
3. Test your changes thoroughly
4. Submit a clear description of your changes

## Code of Conduct

- Be respectful and inclusive
- Focus on constructive feedback
- Help others learn and improve

## Questions?

Feel free to open an issue if you have questions or need help with your contribution.
