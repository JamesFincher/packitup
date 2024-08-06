# PackItUp

## 📦 Project Structure Generator and Documentation Tool

PackItUp is a powerful and flexible command-line tool designed to generate comprehensive documentation of your project's structure. It creates a detailed overview of your project's files and directories, making it easier to understand, share, and maintain your codebase.

## 🌟 Features

- 🌳 Generate project structure in tree format
- 📄 Include file contents (optional)
- 📊 Provide file metadata (size, last modified date, permissions)
- 🎨 Multiple output formats (Markdown, JSON, YAML)
- 🧹 Respect .gitignore patterns
- 🚫 Customizable file/directory exclusions
- 📦 Compress output (optional)
- 📏 Customizable file size limits
- 📋 Automatic clipboard copy of output

## 🛠 Installation

1. Clone the repository:

   ```
   git clone https://github.com/yourusername/packitup.git
   cd packitup
   ```

2. Install the required dependencies:

   ```
   pip install colorama pyperclip pyyaml tqdm
   ```

3. Make the script executable (Unix-based systems):
   ```
   chmod +x packitup.py
   ```

## 🚀 Usage

The basic usage of PackItUp is:

```
python packitup.py [OPTIONS] [PATH]
```

If no path is specified, PackItUp will use the current directory.

### 🎛 Options

- `-t, --tree`: Generate file tree only (no file contents)
- `-l, --list`: List files and directories in the specified directory
- `-s, --singlefile`: Ignore file splitting and return as a single file
- `-p, --purge`: Purge all saved PackItUp data
- `-f, --format {markdown,json,yaml}`: Output format (default: markdown)
- `-m, --max-size BYTES`: Maximum file size in bytes (default: 5MB)
- `-c, --compress`: Compress the output files
- `-e, --exclude PATTERN [PATTERN ...]`: Additional patterns to exclude
- `--no-content`: Exclude file contents, only include metadata

## 📚 Examples

### 1. Basic Usage

Generate a Markdown report of the current directory:

```
python packitup.py
```

This will create a Markdown file with the project structure, including file contents (up to 5MB per file) and metadata.

### 2. Specify a Different Directory

Generate a report for a specific project:

```
python packitup.py /path/to/your/project
```

### 3. Generate Only the File Tree

To get a quick overview without file contents:

```
python packitup.py -t
```

### 4. Change Output Format

Generate a JSON report:

```
python packitup.py -f json
```

Or a YAML report:

```
python packitup.py -f yaml
```

### 5. Customize File Size Limit

Set the maximum file size to 10MB:

```
python packitup.py -m 10000000
```

### 6. Exclude Specific Patterns

Exclude all .log and .tmp files:

```
python packitup.py -e *.log *.tmp
```

### 7. Generate a Compressed Output

Create a zip file containing the report:

```
python packitup.py -c
```

### 8. Exclude File Contents

Generate a report with only metadata, no file contents:

```
python packitup.py --no-content
```

### 9. Combine Multiple Options

Generate a compressed JSON report with a 10MB file size limit, excluding .log files and file contents:

```
python packitup.py -f json -m 10000000 -c -e *.log --no-content
```

## 📂 Output

PackItUp generates its output in a new directory named `<project_name>_structure_<timestamp>`. The main output file will be in this directory, named `<project_name>_structure_<timestamp>.<format>`.

If the compress option is used, a zip file will be created in the same directory.

The generated content is automatically copied to your clipboard for easy sharing.

## 🧹 Cleaning Up

To remove all PackItUp generated data:

```
python packitup.py -p
```

This will delete the `.packitup` directory in your home folder and any local output directories.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

- Thanks to all the open-source libraries that made this project possible.
- Special thanks to the Python community for their continuous support and inspiration.

---

Happy documenting! 📚✨
