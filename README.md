# Zed Snippets

A collection of code snippets for the [Zed editor](https://zed.dev/).

## Installation

Copy the snippet files to your Zed configuration directory:

```bash
# Create the snippets directory if it doesn't exist
mkdir -p ~/.config/zed/snippets

# Copy all snippet files
cp *.json ~/.config/zed/snippets/
```

Or you can clone the directory into `~/.local/share/zed/extensions/installed/`

Alternatively, use the `snippets: open folder` action in Zed to navigate to the snippets directory.

## File Structure

Zed uses pure JSON format for snippets (no comments). Each file is named according to the language scope:

| File                | Language Scope                      |
| ------------------- | ----------------------------------- |
| `snippets.json`     | Global (available in all languages) |
| `javascript.json`   | JavaScript & JSX                    |
| `typescript.json`   | TypeScript                          |
| `markdown.json`     | Markdown                            |
| `org.json`          | Org mode                            |
| `shell script.json` | Shell Script                        |
| `json.json`         | JSON                                |

## Snippet Format

Each snippet follows this structure:

```json
{
	"Snippet Name": {
		"prefix": "trigger",
		"body": ["line 1", "line 2 with ${1:placeholder}"],
		"description": "Optional description"
	}
}
```

### Placeholders

- `$1`, `$2` - Tab stops
- `${1:defaultValue}` - Placeholder with default value
- `$0` - Final cursor position
- Placeholders with the same number are linked

### Escaping

If the snippet contains the `$` symbol outside of a placeholder, it must be escaped with two backslashes: `\\$var`

## Available Snippets

### JavaScript & TypeScript

| Prefix | Description                 |
| ------ | --------------------------- |
| `f()`  | Arrow function (expression) |
| `fn()` | Arrow function (block)      |

### Shell Script

| Prefix   | Description                                                                      |
| -------- | -------------------------------------------------------------------------------- |
| `!b`     | Bash shebang                                                                     |
| `f()`    | Basic function                                                                   |
| `func()` | Full-featured function with argument parsing, help text, and dependency checking |

### Markdown

| Prefix        | Description                |
| ------------- | -------------------------- |
| `!n`          | Note admonition            |
| `!t`          | Tip admonition             |
| `!i`          | Important admonition       |
| `!c`          | Caution admonition         |
| `!w`          | Warning admonition         |
| `!!m`         | Embed media                |
| `!\``         | Code block                 |
| `!!fold`      | Foldable details block     |
| `ascii:style` | ASCII art scroll fix style |
| `ascii:block` | ASCII art code block       |

### Org Mode

| Prefix | Description   |
| ------ | ------------- |
| `!+s`  | Source block  |
| `!+q`  | Quote block   |
| `!+e`  | Example block |
| `!+v`  | Verse block   |
| `!+n`  | Note block    |
| `!+w`  | Warning block |
| `!+c`  | Comment block |

### JSON

| Prefix    | Description             |
| --------- | ----------------------- |
| `vs:snip` | VSCode snippet template |

## Known Limitations

- Only the first prefix is used when a list of prefixes is provided
- Currently only JSON snippet file format is supported

## Contributing

Feel free to add more snippets! Just follow the existing format and naming conventions.

## License

MIT
