# remove-hyperlink Script

## Description
This script removes hyperlink formatting from a Markdown file. It can process two types of hyperlink formats:
1. `[[text\]](url)` 
2. `[text](url)`

It reads an input Markdown file and either outputs the result to the terminal or writes it to an output file if specified.

## Usage

```bash
usage: ./remove-hyperlink input.md [output.md]
```

### Arguments:
- `input.md` (Required)
  
  The path to the input Markdown file containing hyperlinks.
- `output.md` (Optional)
  
  The path to the output file where the modified Markdown content will be saved. If not provided, the output will be displayed in the terminal.

### Example Usage:

1. **Remove hyperlinks and display in the terminal:**
   ```bash
   ./remove-hyperlink input.md
   ```

2. **Remove hyperlinks and save the result to an output file:**
   ```bash
   ./remove-hyperlink input.md output.md
   ```

## Script Explanation

### Functions:
- `usage()`

  Displays how to use the script and exits if the input arguments are incorrect.

### Steps:
1. The script checks if at least one argument is provided.
2. It verifies the existence of the input file.
3. If a second argument (output file) is provided, the script removes the hyperlinks and writes the modified content to the output file.
4. If no output file is provided, the script displays the modified content in the terminal.

### Regular Expressions:
- `s/\[\[([^\\\]]+)\\?\]\]\([^)]*\)/\1/g`

  Removes hyperlinks of the format `[[text\]](url)`.
- `s/\[([^]]+)\]\([^)]*\)/\1/g`

  Removes standard hyperlinks of the format `[text](url)`.

## License
This script is provided "as is" and is free to use and modify under the MIT License.
