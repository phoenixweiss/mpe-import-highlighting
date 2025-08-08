# MPE Import Highlighting

Syntax highlighting for the `@import` directive used by **Markdown Preview Enhanced** (MPE) to [import external files](https://shd101wyy.github.io/markdown-preview-enhanced/#/file-imports?id=import-external-files) inside Markdown documents.

This extension injects a small TextMate grammar into the built-in Markdown grammar so that lines like:

```md
@import "./includes/example_code.py" { line_end=-1 cmd="python" }
```

get proper tokenization:

- `@import` as a keyword
- path (quoted or unquoted) as a string
- option block `{ ... }` with keys, `=`, numbers/booleans/strings, commas

> **Note**: This is only syntax highlighting; it does not execute imports or render previews. Use the original [MPE extension](https://shd101wyy.github.io/markdown-preview-enhanced/) for previewing.

## Requirements

- VS Code 1.103+ (should work on slightly older versions too)
- Markdown files (`.md`)

## Installation

### From VSIX (local)

1. Clone the repo:

   ```bash
   git clone https://github.com/<your-account>/mpe-import-highlighting.git
   cd mpe-import-highlighting
   ```

2. Package (optional):

   ```bash
   npm i -g vsce
   vsce package
   code --install-extension mpe-import-highlighting-0.0.1.vsix
   ```

### From source (development)

- Open the folder in VS Code and press **F5** to launch an Extension Development Host.
- Open a Markdown file and type an `@import ...` line to see the tokens.

## Scope & Limitations

- Matches `@import` at the **start of a line** (common MPE style).
- Does not highlight inside fenced code blocks (by design).
- Token colors come from your theme via standard scopes (`keyword.control`, `string.quoted`, `constant.numeric`, etc.).

## Related & recommended Extensions

- **Markdown Preview Enhanced** — `shd101wyy.markdown-preview-enhanced` (functional preview)
- **Markdown All in One** — `yzhang.markdown-all-in-one` (optional but handy for general Markdown authoring)

## Author

Created and maintained by **PAVEL TKACHEV (phoenixweiss)**.

## License

**MPE Import Highlighting** is open-source software available under the MIT license.
