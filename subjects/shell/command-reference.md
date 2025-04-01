# Command Reference

## Shell Commands

*   **ls** [<options>] [<files>]
    *   **Explanation:** Lists directory contents. [1, 2]
    *   **Options:**
        *   `-l`: Long listing, displaying file size, ownership, permissions, etc. [2]
        *   `-t`: Sort by timestamp (latest first). [2]
        *   `-r`: Reverse the listing order. [2]
        *   `-a`: List all files, including hidden files (starting with `.`). [2]
*   **mkdir** <directory> [...]
    *   **Explanation:** Creates one or more new directories. [3]
*   **cd** <directory>
    *   **Explanation:** Changes the current directory. If no directory is named, it changes to the home directory. `..` refers to the parent directory. [3]
*   **pwd**
    *   **Explanation:** Prints the name of the current (working) directory. [2]
*   **mv** <file1> <file2>
    *   **Explanation:** Renames `file1` to `file2`. If `file2` exists, it is overwritten. [4]
*   **mv** <files> <directory>
    *   **Explanation:** Moves the listed `files` into the specified `directory`. [4]
*   **cp** <file1> <file2>
    *   **Explanation:** Copies `file1` to `file2`. [4]
*   **cp** <files> <directory>
    *   **Explanation:** Copies the listed `files` into the specified `directory`. [4]
*   **ln** <file1> <file2>
    *   **Explanation:** Creates a hard link between `file1` and `file2`. [4]
*   **cat** <files>
    *   **Explanation:** Concatenates and prints the contents of the listed `files` to standard output. [5]
*   **rm** <files>
    *   **Explanation:** Removes the named `files` (not directories). Use `-r` for recursive removal of directories. [5]
*   **head** -<N> <file>
    *   **Explanation:** Displays the first `N` lines of the named text `file`. [6]
*   **tail** -<N> <file>
    *   **Explanation:** Displays the last `N` lines of the named text `file`. [6]
*   **less** <file>
    *   **Explanation:** Allows scrolling through the contents of a `file`. [6]
*   **echo** <text>
    *   **Explanation:** Displays a line of text to standard output. [7]
*   **wget** <URL>
    *   **Explanation:** Downloads the file from the specified `URL`. [6]
*   **wc** [<options>] [<file>]
    *   **Explanation:** Counts the number of lines, words, and characters in a `file`. [8]
    *   **Options:**
        *   `-l`: Displays only the number of lines. [9]
*   **man** <name>
    *   **Explanation:** Displays the manual page for the named command or topic. [3]
*   **chmod** <octal mode> <files>
    *   **Explanation:** Changes the file permissions of the specified `files` using an octal mode. [10, 11]
*   **chmod** <symbolic mode> <files>
    *   **Explanation:** Changes the file permissions of the specified `files` using a symbolic mode (e.g., `ugo+rwx`). [10, 11]
*   **date**
    *   **Explanation:** Prints the current date and time. [12]
*   **ps** [<options>]
    *   **Explanation:** Prints information about the current processes. [13]
    *   **Options:**
        *   `-l`: Provides a long listing with more information. [14]
        *   `-f`: Provides more information about the command. [14]
*   **top**
    *   **Explanation:** Displays dynamic real-time views of running processes. [14]
*   **kill** [<options>] <PIDs>
    *   **Explanation:** Sends a signal to the specified processes identified by their PIDs. `-9` is a stronger signal. [15]
*   **cut** [-d <delim>] -f <list> <files>
    *   **Explanation:** Extracts sections from each line of the input `files` based on a delimiter. [15]
    *   **Options:**
        *   `-d <delim>`: Specifies the delimiter character. [15]
        *   `-f <list>`: Specifies the fields to be extracted (comma-separated, or a range like `1,5-7`). [15]
*   **paste** [-d <sep>] <files>
    *   **Explanation:** Merges lines of several `files` side by side, separated by a delimiter. [16]
    *   **Options:**
        *   `-d <sep>`: Specifies the delimiter (`<TAB>` is default). [16]
*   **tr** [<options>] <string1> <string2>
    *   **Explanation:** Translates or deletes characters from standard input. [17]
    *   **Options:**
        *   `-c`: Complement the set of characters in `<string1>`. [17]
        *   `-s`: Squeeze multiple contiguous occurrences of characters in `<string1>`. [17]
*   **comm** [<options>] <file1> <file2>
    *   **Explanation:** Compares two sorted `files` line by line. [18]
    *   **Options:**
        *   `-1`: Suppress lines unique to `<file1>`. [18]
        *   `-2`: Suppress lines unique to `<file2>`. [18]
        *   `-3`: Suppress lines common to both files. [18]
*   **uniq** [<options>] <file>
    *   **Explanation:** Removes adjacent duplicate lines from a `file`. [18]
    *   **Options:**
        *   `-c`: Outputs the count of occurrences for each line. [18]
*   **sort** [<options>] <files>
    *   **Explanation:** Sorts lines of text `files`. [19]
    *   **Options:**
        *   `-u`: Removes duplicate lines after sorting. [19]
        *   `-t <char>`: Specifies the field separator. [19]
        *   `-k <start>[<type>][,<end>[<type>]`: Specifies the sort key (field number). [20]
*   **grep** [<options>] <pattern string> <file> [...]
    *   **Explanation:** Searches for the `<pattern string>` in one or more `files`. [21]
    *   **Options:**
        *   `-i`: Makes the search case-insensitive. [22]
        *   `-n`: Prepends the line numbers of the matching lines. [22]
        *   `-v`: Inverts the match, showing only non-matching lines. [22]
*   **test** <test expression>
    *   **Explanation:** Evaluates a `<test expression>` and returns the result as an exit status (0 for true, non-zero for false). [23, 24]
    *   **Common Test Expressions:**
        *   `-d <directory>`: True if the directory exists. [23]
        *   `-f <file>`: True if the file exists and is a regular file. [23]
        *   `-s <file>`: True if the file exists and has a size greater than zero. [23]
        *   `-n <string>`: True if the string has a non-zero length. [23]
        *   `-z <string>`: True if the string has a zero length. [23]
*   **[[** <test expression> **]]**
    *   **Explanation:** Bash built-in command to evaluate a `<test expression>`. Similar to `test` but with some enhanced features. [24, 25]
    *   **Numeric Comparison Operators (within [[ ]]):**
        *   `-lt`: Less than. [25]
        *   `-ge`: Greater than or equal to. [25]
        *   `-gt`: Greater than. [25]
        *   `-eq`: Equal to. [25]
*   **export** <variable>
    *   **Explanation:** Marks a shell variable for export to the environment of subsequently executed commands. [26]
*   **du** [<options>] [<files>]
    *   **Explanation:** Estimates file space usage. [26]

## Shell Scripting Constructs

*   **if** <condition> **then** <statements> [**elif** <condition> **then** <statements>] ... [**else** <statements>] **fi**
    *   **Explanation:** Conditional execution of commands based on the exit status of the `<condition>`. [27]
*   **case** <expression> **in** <pattern> [| <pattern> ...] **)** <statements> **;;** ... [ **\*** **)** <statements> **;;** ] **esac**
    *   **Explanation:** Executes a block of `<statements>` corresponding to the first matched `<pattern>` for the given `<expression>`. `*` acts as the default case. [28]
*   **for** <name> **in** <list> **do** <commands> **done**
    *   **Explanation:** Iterates over a whitespace-separated `<list>` of strings, assigning each item to the variable `<name>` and executing the `<commands>` in each iteration. [29]
*   **for** (( <initialize loop> ; <test loop exit> ; <update> )) **do** <statements> **done**
    *   **Explanation:** C-style for loop with initialization, exit condition test, and update expression. [9]
*   **while** <condition> **do** <statements> **done**
    *   **Explanation:** Repeatedly executes `<statements>` as long as the `<condition>` evaluates to true (exit status 0). [30]
*   **break**
    *   **Explanation:** Exits the innermost enclosing `for` or `while` loop. [30]
*   **shift**
    *   **Explanation:** Shifts the command-line arguments one position to the left. `$1` becomes the old `$2`, `$2` becomes the old `$3`, and so on. `$#` (number of arguments) is decremented. [31]

## Shell Arithmetic

*   **$((** <expression> **))**
    *   **Explanation:** Evaluates an arithmetic `<expression>` and substitutes the result. Supports integer arithmetic operators like `+`, `-`, `*`, `/`, `%`, `&&`, `||`, `!`, etc. [32]

## find Command

*   **find** [<path>] [<expression>]
    *   **Explanation:** Searches for files in the directory hierarchy rooted at each specified `<path>`. If no path is given, the current directory is used. The `<expression>` specifies criteria and actions. [33]
    *   **Common Tests:**
        *   `-name <file pattern>`: Matches files with the given name pattern (supports wildcards like `*`, `?`, `[]`). [34]
        *   `-type <c>`: Matches files of the specified type (`d` for directory, `f` for file, `l` for symbolic link). [34]
        *   `-newer <file>`: Matches files modified more recently than the specified `file`. [34]
        *   `-perm <mode>`: Matches files with the specified permissions. [35]
    *   **Common Actions:**
        *   `-print`: Prints the full pathname of the matched file. [34]
        *   `-exec <command> {} \;`: Executes the specified `<command>` on each matched file. `{}` is replaced by the current filename, and `\;` terminates the command. [34]

## Regular Expressions (used with grep, sed, awk)

*   `.`: Matches any single character. [36]
*   `?`: Matches zero or one occurrence of the preceding character. [36]
*   `[<set>]`: Matches any single character from the `<set>`. [36]
*   `[^<set>]`: Matches any single character NOT in the `<set>`. [36]
*   `*`: Matches zero or more occurrences of the preceding character/group. [36]
*   `.*`: Matches zero or more occurrences of any character. [37]
*   `^`: Matches the beginning of a line. [37]
*   `$`: Matches the end of a line. [37]
*   `\`: Escapes the special meaning of the next character. [37]
*   `\(` `\)`: Captures the matched group for later reuse (using `\1`, `\2`, etc.). [37, 38]

## sed Command (Stream Editor)

*   **sed** [<options>] [<script>] [<file> ...]
    *   **Explanation:** A stream editor used for in-place modification of text. [39, 40]
    *   **Options:**
        *   `-e <script>`: Applies the `<script>` to the input. Can be used multiple times. [40]
        *   `-f <script_file>`: Applies the commands in the `<script_file>` to the input. [40]
        *   `-n`: Suppresses default output. Use with `p` to print specific lines. [40]
    *   **Common Commands (within script):**
        *   `s/<regular expression>/<replacement>/[g]`: Substitutes the first match of the `<regular expression>` with the `<replacement>`. `g` flag replaces all occurrences on the line. [41] `&` in the replacement refers to the entire matched string.
        *   `d`: Deletes the lines matching the address. [42]
        *   `p`: Prints the lines matching the address (often used with `-n`). [42]
        *   `l`: Prints the lines matching the address in a more explicit format (shows non-printable characters). [42]
    *   **Addresses:** Can be line numbers, `$` (last line), `/regex/`, or ranges (e.g., `10,20`, `/start/,/end/`). [43, 44]

## git Commands (Version Control)

*   **git init** [<name>]
    *   **Explanation:** Creates a new empty Git repository in the current directory or the specified `<name>` directory. [45, 46]
*   **git status**
    *   **Explanation:** Shows the status of the working tree and staging area. [46]
*   **git add** <files>
    *   **Explanation:** Adds the specified `<files>` to the staging area. `git add .` stages all changes in the current directory. [45, 47]
*   **git commit** [<options>]
    *   **Explanation:** Records changes to the repository. [45, 47]
    *   **Options:**
        *   `-m <message>`: Provides a commit message on the command line. [47]
        *   `-a`: Automatically stages all modified and deleted files before committing (excluding untracked files). [47]
*   **git merge** <branch>
    *   **Explanation:** Integrates changes from the specified `<branch>` into the current branch. [46, 48]
*   **git fetch** [<remote>]
    *   **Explanation:** Downloads objects and refs from another repository (usually a remote repository). [46]
*   **git pull** [<remote>]
    *   **Explanation:** Fetches from and integrates with another repository or a local branch. Equivalent to `git fetch` followed by `git merge`. [46]
*   **git clone** <repo>
    *   **Explanation:** Creates a copy of the repository at the specified `<repo>` URL. [49]
*   **git push** [<remote>]
    *   **Explanation:** Updates remote refs along with associated objects. [49]
*   **git diff** [<options>] [<commit>] [<commit>] [<file>]
    *   **Explanation:** Shows changes between commits, the working tree, and the staging area. [49, 50]
    *   **Options:**
        *   `--cached`: Shows changes between the staging area and the last commit. [49, 50]
        *   `<commit>`: Compares against a specific commit. [50]
        *   `<commit> <commit>`: Compares between two specific commits. [50]
        *   `<file>`: Limits the comparison to a specific file or directory. [50]
*   **git checkout** [<options>] <commit> [<file>]
    *   **Explanation:** Switches branches or restores working tree files. [51]
    *   **Options:**
        *   `-b <name>`: Creates and switches to a new branch named `<name>`. [52]
        *   `<commit>`: The commit or branch to travel to. [51]
        *   `<file>`: Restores the specified file to the version in the given commit. [51]
*   **git branch** [<options>] [<name>]
    *   **Explanation:** Lists, creates, or deletes branches. [52]
    *   **Options:**
        *   `-m <name>`: Renames the current branch to `<name>`. [52]
        *   `-d <name>`: Deletes the branch `<name>` (must be fully merged). [52]

## awk Command (Pattern Scanning and Processing Language)

*   **gawk** [<options>] [<awk script>] [<file> ...]
    *   **Explanation:** The GNU version of `awk`, used for pattern scanning and processing of input files. [53]
    *   **Options:**
        *   `-F <char>`: Sets the input field separator to `<char>`. [54]
        *   `-f <file>`: Reads the `awk` script from the specified `<file>`. [54]
        *   `-v <variable>=<value>`: Assigns a value to a variable before the script begins execution. [54]
    *   **Basic Syntax:** `[<pattern>] { <actions> }`. If no pattern is given, the actions are applied to all lines. [53, 55]
    *   **Special Patterns:**
        *   `BEGIN { <actions> }`: Executed before the first line is read. [56]
        *   `END { <actions> }`: Executed after the last line has been read. [56]
    *   **Variables:**
        *   `$0`: The entire current input line. [53]
        *   `$1`, `$2`, ...: The first, second, etc., field of the current input line. [53]
        *   `FS`: Input field separator (default is space or tab). [57]
        *   `OFS`: Output field separator (default is space). [57]
        *   `NF`: Number of fields in the current line. [57]
        *   `NR`: Number of the current input line. [57]
        *   `FILENAME`: Name of the current input file. [57]
        *   `ARGC`: Command-line argument count. [57]
        *   `ARGV`: Array of command-line arguments. [57]
    *   **Operators:** Relational (`==`, `!=`, `<`, `<=`, `>`, `>=`), matching (`~` matches regex, `!~` does not match regex), logical (`&&`, `||`, `!`), arithmetic (`+`, `-`, `*`, `/`, `%`, `^`), assignment (`=`, `+=`, `-=`, etc.). [58-61]
    *   **Statements:** `print [<expression list>] [> file] [>> file] [| command]`, `printf(<format string>, <expression list>) [> ...]`, `if (condition) statement [else statement]`, `for (variable in array) statement`, `for (init; condition; increment) statement`, `while (condition) statement`, `break`, `continue`, `delete array[index]`, `delete array`. [61-65]
    *   **Built-in Functions:** `length(string)`, `substr(string, start, length)`, `sprintf(format, ...)`, `sub(regex, replacement, string)`, `gsub(regex, replacement, string)`, `system(command)`, `getline [variable] [< file | command ]`. [66, 67]
    *   **User-Defined Functions:** `function name(parameter list) { statements; [return value] }`. [68]

## make Command

*   **make** [<options>] [<targets>]
    *   **Explanation:** A utility that controls the generation of executables and other non-source files from the program's source files. Uses a `Makefile`. [69, 70]
    *   **Options:**
        *   `-f <makefile>`: Specifies the makefile to use. [70]
        *   `-j <N>`: Allows `make` to run `N` jobs in parallel. [71]
        *   `-k`: Keeps going to the next target if an error is encountered. [71]
    *   **Makefile Syntax:**
        *   **Rules:** `<target(s)> : <prerequisites>` followed by `<commands>` (each command must start with a tab). [70] The target is what needs to be made, prerequisites are what the target depends on, and commands are the steps to create the target.
        *   **Variables:** `<name> = <value>`. Values are accessed using `$(name)` or `${name}`. [72, 73]
        *   **Wildcards:** `%` matches zero or more characters within a filename pattern. [73]
        *   **Automatic Variables:**
            *   `$@`: The target of the rule. [73]
            *   `$<`: The first prerequisite. [73]
            *   `$^`: A space-separated list of all prerequisites. [73]
            *   `$*`: The part of the target name that matched the wildcard `%`. [73]
        *   **Special Targets:**
            *   `.PRECIOUS`: Prevents `make` from deleting intermediate files. [74]

## Markdown Syntax (for documentation)

*   **Headings:**
    *   `# Heading`: Level 1 heading [75]
    *   `## Sub-heading`: Level 2 heading [76]
    *   `Heading ======`: Level 1 heading [75]
    *   `Sub-heading ---------------`: Level 2 heading [75]
*   **Emphasis:**
    *   `_italic_` or `*italic*`: Italic [76]
    *   `**bold**` or `__bold__`: Bold [76]
    *   `` `monospace` ``: Monospace (fixed font) [76]
*   **Lists:**
    *   Numbered list: `1. Item 1`, `2. Item 2` [76]
    *   Bullet list: `* Item 1`, `- Item 2`, `+ Item 3` [76]
*   **Blockquotes:**
    *   `> Blockquote line` [77]
*   **Links:**
    *   `[Link text](URL)` [77]
*   **Images:**
    *   `![Alt text](URL "Optional title")` [77]