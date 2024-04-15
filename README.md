# Bash-Scripting-The-Definitive-Guide
Streamline your Bash scripts with expert guidance on best practices and code organization.

---

**Bash Scripting Best Practices**

**1. Shebang Line**

Start your script with a shebang line to specify the interpreter:

```bash
#!/bin/bash
```

**2. Script Info**

Include script information such as name, date, author, and description:

```bash
################################################################################
# Name:        myscript.sh
# Date:        2024-04-14
# Author:      Sam
# Description: My awesome script.
################################################################################
```

**3. Figlet or Toilet**

Use figlet or toilet to generate the name of the script in large letters, commented out:

```bash
figlet "My Script" | sed 's/^/# /'
```
```bash
# ▙▗▌▌ ▌  ▞▀▖▞▀▖▛▀▖▜▘▛▀▖▀▛▘
# ▌▘▌▝▞   ▚▄ ▌  ▙▄▘▐ ▙▄▘ ▌ 
# ▌ ▌ ▌   ▖ ▌▌ ▖▌▚ ▐ ▌   ▌ 
# ▘ ▘ ▘▀▀▀▝▀ ▝▀ ▘ ▘▀▘▘   ▘ 
```
**4. Source External Scripts**

In this section of your script, you should source external scripts that provide additional functionality. Use the full path to the script and include a comment explaining what it does, along with a link to the project page for reference.

Example:

```bash
# Source external scripts for additional functionality

# Get extract flags from arguments as variables using: https://github.com/AmosNimos/flag
. /path/to/flag_utility
flag_utility "$@"
```

Make sure to replace `/path/to/flag/utility` with the actual path to the external script in your system. This practice helps maintain transparency and allows users to understand the purpose of the sourced script.

**5. Print Help**

Add a function to print the script's help information:

```bash
print_help() {
    echo "Usage: $0 [OPTIONS]"
    echo "Options:"
    echo "  -h, --help    Show help information"
}
```

You can use a here document (heredoc) to create multi-line strings in Bash, which is particularly useful for printing help messages. Here's an example of how you can define the help message using a heredoc:

```bash
print_help() {
    cat << EOF
Usage: $0 [OPTIONS]

Options:
  -h, --help    Show help information
  -v, --version Show version information
EOF
}
```

In this example, `cat << EOF` starts the heredoc, and `EOF` marks the end of the heredoc. The text between `EOF` and `EOF` will be treated as a multi-line string and printed by `cat`. You can adjust the help message content as needed.

**6. Initializing Global Variables**

Initialize global variables using capital letters and no spaces:

```bash
GLOBAL_VARIABLE="value"
```

**7. Reading Arguments**

Read and parse command-line arguments using if or case statements:

```bash
if [[ "$1" == "-h" || "$1" == "--help" ]]; then
    print_help
    exit 0
fi
```

**8. Functions**

Define your functions after argument parsing:

```bash
my_function() {
    local local_variable="value"
    echo "Function executed"
}
```

**10. Additional Notes**

- Use comments generously to explain your code's logic and purpose.

---
