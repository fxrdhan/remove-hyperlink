# Markdown Link Remover Script

## Description
This script removes hyperlink formatting from Markdown files. It processes multiple types of hyperlinks and URLs:

1. Wiki-style links: `[[text\]](url)`
2. Standard Markdown links: `[text](url)`
3. Bare URLs: `https://example.com`

## Usage
```bash
./remove-hyperlink input.md [output.md]
```

### Arguments
- `input.md` (Required)  
  Path to the input Markdown file containing hyperlinks.
  
- `output.md` (Optional)  
  Path to the output file where the modified content will be saved.
  If not specified, output will be displayed in the terminal.

### Examples
```bash
# Display modified content in terminal
./remove-hyperlink input.md

# Save modified content to a file
./remove-hyperlink input.md output.md
```

## Features

### Error Handling
- Input file validation
  - Existence check
  - Read permission check
- Output location validation
  - Directory existence check
  - Write permission check
  - File permission check if file exists
- Clear error messages directed to stderr

### Exit Codes
- `0`: Success
- `1`: Invalid arguments
- `2`: File not found
- `3`: Permission error

## Function Documentation

### Main Functions

#### `main()`
- Entry point of the script
- Handles argument validation and orchestrates the processing flow
- Parameters: Command line arguments (`$@`)

#### `display_usage()`
- Shows detailed usage instructions and examples
- No parameters
- Called when invalid arguments are provided

#### `validate_input_file()`
- Validates the existence and readability of input file
- Parameters: `input_file` (string)
- Exits with appropriate code if validation fails

#### `validate_output_location()`
- Checks if output location is writable
- Parameters: `output_file` (string)
- Validates both directory and file permissions

#### `remove_hyperlinks()`
- Processes the Markdown file to remove hyperlinks
- Parameters: `input_file` (string)
- Returns: Modified content with links removed

#### `process_file()`
- Handles file processing and output generation
- Parameters: 
  - `input_file` (string)
  - `output_file` (string, optional)

### Regular Expressions

```sed
# Remove wiki-style links
s/\[\[([^\\\]]+)\\?\]\]\([^)]*\)/\1/g

# Remove standard Markdown links
s/\[([^]]+)\]\([^)]*\)/\1/g

# Remove bare URLs
s/https?:\/\/[[:alnum:]_\/.?=&#-]+//g

# Clean up extra spaces
s/[[:space:]]+/ /g
```

## Error Messages

The script provides clear error messages for various scenarios:

```bash
# Invalid usage
Usage: remove-hyperlink input.md [output.md]
...

# File not found
Error: File 'input.md' not found.

# Permission errors
Error: Cannot read file 'input.md'. Check permissions.
Error: Directory 'output_dir' does not exist.
Error: Cannot write to directory 'output_dir'. Check permissions.
Error: Cannot write to file 'output.md'. Check permissions.
```

## Success Messages

```bash
Success: Hyperlinks have been removed and saved to 'output.md'.
```

## Dependencies
- Bash shell (version 4.0 or higher recommended)
- sed (GNU sed recommended)

## License
This script is provided under the MIT License.
