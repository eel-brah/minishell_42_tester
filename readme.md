# 🐚 Minishell Tester

A comprehensive testing tool for the [Minishell](https://github.com/eel-brah/minishell)  project that compares your shell implementation against bash behavior.

## 🔎 Overview

Minishell Tester is a Python script designed to thoroughly test shell implementations by comparing their output with bash. The tool runs a series of predefined tests across multiple categories and provides detailed results of any discrepancies.

If your minishell has a different prompt format (adding lines at the beginning or the end), you may need to adjust the line skipping parameters:
- Use `--lines` to set how many lines to skip from the beginning (for prompt lines)
- Use `--endlines` to set how many lines to remove from the end

You can run this to debug and compare outputs:
```bash
python3 tester.py --test
```

---

## 📦 Features

- **Comprehensive Test Suite**: Tests various shell functionalities including builtins, redirections, syntax, wildcards, logical operators, and mixed commands
- **Detailed Comparison**: Compares your shell's output and exit codes with bash
- **Organized Test Categories**: Tests are organized into mandatory and bonus categories
- **Detailed Failure Reports**: Provides detailed information about failed tests
- **Export Failed Tests**: Automatically exports details of failed tests to a file for further analysis

---

## Installation

1. Clone this repository or download the script files
2. Make sure you have Python 3 installed
3. Place the minishell tester in the same directory as your minishell project or specify the path to your minishell executable

---

## 🚀 Usage

```bash
python3 tester.py [options]
```

### 🔧 Options

| Option             | Description                                                    |
|--------------------|----------------------------------------------------------------|
| `-p`, `--path`     | Path to your `minishell` executable (default: `./minishell`)   |
| `-b`, `--bonus`    | Run **bonus tests** (wildcards, logical operators, mix)        |
| `-l`, `--lines`    | Number of lines to skip from the top of minishell output       |
| `-e`, `--endlines` | Number of lines to skip from the end of minishell output       |
| `-c`, `--category` | Run a specific test category (`builtin`, `redirection`, etc.)  |
| `-t`, `--test`     | Run a **single test** to debug and compare outputs             |

---

## 🔍 Examples

### Run all mandatory tests:
```bash
python3 tester.py
```

### Run all tests including bonus:
```bash
python3 tester.py --bonus
```

### Run only builtin tests:
```bash
python3 tester.py --category builtin
```

### Compare a basic `echo hi` command output:
```bash
python3 tester.py --test
```

### Customize prompt removal (if your prompt spans more lines):
```bash
python3 tester.py -l 2
```

---

## 🧪 Test Structure

### Mandatory
1. **Builtin Commands**: Tests implementation of shell builtin commands
2. **Redirections**: Tests input/output redirection functionality
3. **Syntax**: Tests handling of syntax errors and edge cases

### Bonus
1. **Wildcards**: Tests wildcard pattern matching
2. **Logical Operators**: Tests AND (&&) and OR (||) operators
3. **Mixed Commands**: Tests complex combinations of various shell features

You can add new tests by adding them to minishell_tests.py

## 📂 Output

The tester provides real-time feedback during test execution, showing:
- Test category headers with ASCII art
- Pass/fail status for each test
- Expected vs. actual output for failed tests
- A summary of results at the end

A `failed_tests.txt` file is generated in the project directory containing details of all failed tests for easier debugging.

## ✅ Success Criteria

A test is considered successful if:
- `stdout` matches Bash.
- `return code` matches Bash.
- If failing, both Bash and Minishell produce `stderr`.

---

## Dependencies

- Python 3.x
- Standard Python libraries (no external packages required)

## 👥 Authors
By me [GitHub Profile](https://github.com/eel-brah)
With the help of: 
- [AhmedMokhtari](https://github.com/AhmedMokhtari)
- [imenyoo2](https://github.com/imenyoo2)
