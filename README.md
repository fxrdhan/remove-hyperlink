# Remove Hyperlink

Remove Hyperlink is a Bash script designed to remove all types of hyperlinks from Markdown files. It supports various Markdown link formats, including standard links, wiki-style links, reference links, as well as unformatted URLs.

## Features

- **Remove Standard Links:** Removes links in the format `[text](URL)`.
- **Remove Wiki Style Links:** Removes links in the format `[[text]](URL)`.
- **Remove Reference Links:** Removes links in the format `[text][ref]` and their definitions.
- **Remove Unformatted URLs:** Removes URLs that appear directly in the text.
- **Special Character Handling:** Manage links with special characters and parentheses.
- **Remove Empty Lines:** Delete lines that are empty or contain only spaces after the link removal process.

## Prerequisites

- **Bash shell:** This script is written using Bash and utilizes `sed` for text processing.
- **Execution Permissions:** Make sure the script has execution permissions.

## Installation

1. **Clone Repository:**

    ```bash
    git clone https://github.com/fxrdhan/remove-hyperlink.git
    ```

2. **Navigate to Script Directory:**

    ```bash
    cd remove-hyperlink
    ```

3. **Give the Script Execution Permission:**

    ```bash
    chmod +x remove-hyperlink
    ```

## Usage

This script is used to remove hyperlinks from Markdown files. You can specify an input file and an output file. If the output file is not specified, the result will be displayed in the terminal.

### Syntax

```bash
./remove-hyperlink input.md [output.md]
```

- ``input.md``: The Markdown file to be processed.
- `output.md` _(optional)_: The result file to be saved. If not specified, the result will be displayed in the terminal.

### Usage Example

1. **Display Result in Terminal:**

    ```bash
    ./remove-hyperlink input.md
    ```

2. **Save Results to Output File:**

    ```bash
    ./remove-hyperlink input.md output.md
    ```

    After running the above command, the `output.md` file will contain a version of `input.md` without hyperlinks.

## Example

### Before Processing (`input.md`):

```markdown
This is a [simple link](https://example.com) in a sentence.
Visit the [[wiki page]](https://wiki.example.com) for more information.
Here are the [reference links][1].

[1]: https://referensi.example.com
```

### After Processing (`output.md`):

```markdown
This is a simple link in a sentence.
Visit the wiki page for more information.
Here are the reference link.
```

## Contributions

Contributions to the development of this script are very welcome.

## License

This script is licensed under the [MIT License](LICENSE).

## Support

If you run into problems or have questions, please open an [issue](https://github.com/fxrdhan/remove-hyperlink/issues) in this repository.
