Alright bro 🔥 — here comes **the full master set** of **150 Bash & Linux MCQs** including **answers**.
Everything from **environment variables, commands, redirection, scripting, loops, regex, awk, sed, grep, path execution questions**, and **lab-style what’s-the-output** problems.

Let’s go all in 💪

---

## 🧩 SECTION 1: Environment Variables & Customization (Q1–15)

| #  | Question                                                         | Answer                                        |
| -- | ---------------------------------------------------------------- | --------------------------------------------- |
| 1  | Which command displays the current value of the `HOME` variable? | b) echo $HOME                                 |
| 2  | The `PATH` variable is used to:                                  | b) Store directories searched for executables |
| 3  | Where is the user’s default shell defined?                       | a) /etc/passwd                                |
| 4  | To make alias permanent:                                         | b) ~/.bashrc                                  |
| 5  | Command to list all environment variables:                       | b) env                                        |
| 6  | The `$USER` variable holds:                                      | b) The username                               |
| 7  | To apply `.bashrc` immediately:                                  | b) source ~/.bashrc                           |
| 8  | `.profile` is executed when:                                     | b) A login shell starts                       |
| 9  | `echo $SHELL` prints:                                            | b) Current shell path                         |
| 10 | To see bash executable location:                                 | c) whereis bash                               |
| 11 | To check all defined aliases:                                    | a) alias                                      |
| 12 | Command to remove an alias temporarily:                          | c) unalias name                               |
| 13 | File that runs for every new interactive shell:                  | b) ~/.bashrc                                  |
| 14 | To list only environment variables (not shell vars):             | a) printenv                                   |
| 15 | Command to show current working directory:                       | c) pwd                                        |

---

## 🧩 SECTION 2: File Utilities & Commands (Q16–40)

| #  | Question                                              | Answer                         |       |
| -- | ----------------------------------------------------- | ------------------------------ | ----- |
| 16 | Compare two files line by line:                       | b) diff                        |       |
| 17 | Counts lines, words, characters:                      | b) wc                          |       |
| 18 | List files >1MB:                                      | a) find . -size +1M            |       |
| 19 | Show file type:                                       | b) file file.txt               |       |
| 20 | Sort contents alphabetically:                         | b) sort names.txt              |       |
| 21 | Remove duplicate lines:                               | a) uniq file.txt               |       |
| 22 | Show only unique lines:                               | a) uniq -u file.txt            |       |
| 23 | Display path of command:                              | b) which                       |       |
| 24 | Side-by-side diff:                                    | a) diff -y file1.txt file2.txt |       |
| 25 | Find all `.sh` files:                                 | a) find . -name "*.sh"         |       |
| 26 | Count number of directories in current dir:           | a) find . -type d              | wc -l |
| 27 | Show top 5 lines of a file:                           | b) head -5 filename            |       |
| 28 | Display last 10 lines:                                | c) tail -10 file               |       |
| 29 | Combine and display two files:                        | b) cat file1 file2             |       |
| 30 | Find file by name:                                    | d) locate filename             |       |
| 31 | List only hidden files:                               | c) ls -a                       |       |
| 32 | Sort by file size descending:                         | a) ls -lS                      |       |
| 33 | Count how many `.txt` files exist:                    | a) ls *.txt                    | wc -l |
| 34 | Show only filenames containing “log”:                 | a) ls *log*                    |       |
| 35 | Find files modified within 2 days:                    | c) find . -mtime -2            |       |
| 36 | Find files owned by specific user:                    | a) find /home -user username   |       |
| 37 | Display 3rd field of each line in file.txt using awk: | a) awk '{print $3}' file.txt   |       |
| 38 | Display only first column of file.csv:                | b) cut -d',' -f1 file.csv      |       |
| 39 | Search word “error” in logs ignoring case:            | a) grep -i "error" *.log       |       |
| 40 | Count number of “root” occurrences:                   | c) grep -c "root" /etc/passwd  |       |

---

## 🧩 SECTION 3: IO Streams & Redirection (Q41–55)

| #  | Question                                                  | Answer                      |                   |
| -- | --------------------------------------------------------- | --------------------------- | ----------------- |
| 41 | `>` redirects:                                            | b) output (overwrite)       |                   |
| 42 | `<` redirects:                                            | b) input from file          |                   |
| 43 | `>>` redirects:                                           | c) appends output           |                   |
| 44 | Redirect both stdout and stderr:                          | a) command > out.txt 2>&1   |                   |
| 45 | Pipe operator (`                                          | `) does:                    | a) output → input |
| 46 | Send stdout to file, stderr to screen:                    | a) command > out.txt        |                   |
| 47 | Send stderr only to file:                                 | b) command 2> err.txt       |                   |
| 48 | Suppress all output:                                      | b) command > /dev/null 2>&1 |                   |
| 49 | Copy output to both file and terminal:                    | d) command                  | tee file.txt      |
| 50 | Append both stdout and stderr to same log:                | c) command >> logfile 2>&1  |                   |
| 51 | Redirect input from file1 and output to file2:            | a) command < file1 > file2  |                   |
| 52 | Show only error messages on screen, store output in file: | a) command 1> out.txt       |                   |
| 53 | Command to read user input interactively:                 | c) read var                 |                   |
| 54 | Display current terminal name:                            | d) tty                      |                   |
| 55 | Redirect stderr to stdout:                                | a) 2>&1                     |                   |

---

## 🧩 SECTION 4: Running Scripts & PATH (Q56–70)

| #  | Question                                                    | Answer                                                 |
| -- | ----------------------------------------------------------- | ------------------------------------------------------ |
| 56 | Run script in current shell:                                | c) source script.sh                                    |
| 57 | Run script using interpreter:                               | b) bash script.sh                                      |
| 58 | Make script executable:                                     | a) chmod +x script.sh                                  |
| 59 | Top line `#!/bin/bash` is:                                  | a) shebang                                             |
| 60 | Script at `/home/user/bin/hello.sh` accessible anywhere if: | b) /home/user/bin is in PATH                           |
| 61 | Add custom dir permanently:                                 | a) add `export PATH=$PATH:/home/user/bin` to ~/.bashrc |
| 62 | To execute script in `/usr/local/bin` by name:              | b) script.sh                                           |
| 63 | Run `/tmp/myscript.sh` regardless of location:              | b) /tmp/myscript.sh                                    |
| 64 | Execute script using relative path:                         | a) ./myscript.sh                                       |
| 65 | Find full path to `python`:                                 | b) which python                                        |
| 66 | If `myscript.sh` isn’t executable, which works?:            | d) bash myscript.sh                                    |
| 67 | To reload profile without logout:                           | c) source ~/.profile                                   |
| 68 | Run command in background:                                  | d) ./script.sh &                                       |
| 69 | Find what interpreter runs `.py`:                           | b) file script.py                                      |
| 70 | Print PATH variable:                                        | a) echo $PATH                                          |

---

## 🧩 SECTION 5: Bash Variables & Input/Output (Q71–85)

| #  | Question                                | Answer                                             |       |
| -- | --------------------------------------- | -------------------------------------------------- | ----- |
| 71 | Assign a variable:                      | a) name="Research"                                 |       |
| 72 | Display variable:                       | b) echo $name                                      |       |
| 73 | Read input into variable user:          | a) read user                                       |       |
| 74 | Difference between `echo` and `printf`: | d) printf offers formatted output                  |       |
| 75 | To remove a variable:                   | b) unset var                                       |       |
| 76 | Make variable available to subshells:   | a) export var                                      |       |
| 77 | Default value if variable is unset:     | b) ${var:-default}                                 |       |
| 78 | Concatenate two variables a=1, b=2:     | c) echo "$a$b"                                     |       |
| 79 | Arithmetic addition:                    | a) $((a+b))                                        |       |
| 80 | Prompt user for name and print:         | b) read -p "Enter name: " name; echo "Hello $name" |       |
| 81 | Store command output in variable:       | c) var=$(ls)                                       |       |
| 82 | Count words in variable:                | d) echo $var                                       | wc -w |
| 83 | Check if variable empty:                | b) [ -z "$var" ]                                   |       |
| 84 | Access first script argument:           | a) $1                                              |       |
| 85 | Count total arguments:                  | b) $#                                              |       |

---

## 🧩 SECTION 6: Conditionals & Loops (Q86–100)

| #   | Question                                      | Answer                               |
| --- | --------------------------------------------- | ------------------------------------ |
| 86  | Syntax of if:                                 | a) if [ condition ]; then ... fi     |
| 87  | Check if file exists:                         | b) [ -f file ]                       |
| 88  | Check if directory exists:                    | c) [ -d dir ]                        |
| 89  | Check string equality:                        | a) [ "$a" = "$b" ]                   |
| 90  | For loop syntax:                              | b) for i in {1..5}; do echo $i; done |
| 91  | While loop syntax:                            | c) while [ condition ]; do ...; done |
| 92  | If-elif-else ends with:                       | b) fi                                |
| 93  | Case statement ends with:                     | c) esac                              |
| 94  | To test numeric comparison:                   | b) -eq, -ne, -lt, -gt                |
| 95  | Loop over all `.txt` files:                   | a) for f in *.txt; do echo $f; done  |
| 96  | Break a loop:                                 | c) break                             |
| 97  | Skip current iteration:                       | b) continue                          |
| 98  | Test if variable non-empty:                   | b) [ -n "$var" ]                     |
| 99  | To test multiple conditions:                  | c) [[ $a -gt 2 && $b -lt 5 ]]        |
| 100 | Execute a command only if previous succeeded: | a) command1 && command2              |

---

## 🧩 SECTION 7: Functions & getopts (Q101–110)

| #   | Question                                    | Answer                                   |
| --- | ------------------------------------------- | ---------------------------------------- |
| 101 | Define a function:                          | a) function name() { commands; }         |
| 102 | Return value from function:                 | c) return 0                              |
| 103 | Call function:                              | b) name                                  |
| 104 | To access first argument inside function:   | a) $1                                    |
| 105 | To define function without keyword:         | c) name() { echo hi; }                   |
| 106 | getopts is used to:                         | b) parse command-line options            |
| 107 | Inside getopts, variable containing option: | a) $OPTARG                               |
| 108 | getopts loop usually starts as:             | b) while getopts ":ab:" opt; do ... done |
| 109 | To check function list:                     | a) declare -f                            |
| 110 | To export a function to subshell:           | d) export -f funcname                    |

---

## 🧩 SECTION 8: Regex, grep, sed, awk (Q111–135)

| #   | Question                                  | Answer                                                    |          |         |
| --- | ----------------------------------------- | --------------------------------------------------------- | -------- | ------- |
| 111 | Find lines containing “error”:            | a) grep error file                                        |          |         |
| 112 | Find lines not containing “error”:        | b) grep -v error file                                     |          |         |
| 113 | Case-insensitive grep:                    | a) grep -i pattern file                                   |          |         |
| 114 | Count matching lines:                     | b) grep -c pattern file                                   |          |         |
| 115 | Search recursively:                       | c) grep -r "main" *                                       |          |         |
| 116 | Show line numbers:                        | d) grep -n pattern file                                   |          |         |
| 117 | Replace “foo” with “bar”:                 | a) sed 's/foo/bar/' file                                  |          |         |
| 118 | Replace globally on each line:            | b) sed 's/foo/bar/g' file                                 |          |         |
| 119 | Delete blank lines:                       | c) sed '/^$/d' file                                       |          |         |
| 120 | Print only matching part:                 | d) grep -o word file                                      |          |         |
| 121 | In awk, print 2nd field:                  | a) awk '{print $2}' file                                  |          |         |
| 122 | Print lines where field 3 > 50:           | b) awk '$3 > 50' file                                     |          |         |
| 123 | Print with field separator “,”:           | c) awk -F',' '{print $1}' file                            |          |         |
| 124 | Print last field:                         | d) awk '{print $NF}' file                                 |          |         |
| 125 | sed command to delete line 5:             | a) sed '5d' file                                          |          |         |
| 126 | grep regex for lines starting with “A”:   | b) grep '^A' file                                         |          |         |
| 127 | grep regex for lines ending with “.sh”:   | c) grep '.sh$' file                                       |          |         |
| 128 | Replace “cat” only if whole word:         | a) sed 's/\bcat\b/dog/g' file                             |          |         |
| 129 | Count unique words in file:               | b) tr ' ' '\n' < file                                     | sort     | uniq -c |
| 130 | awk to sum numbers in first column:       | c) awk '{sum+=$1} END{print sum}' file                    |          |         |
| 131 | sed replace only 2nd occurrence per line: | d) sed 's/foo/bar/2' file                                 |          |         |
| 132 | grep OR condition for “yes” or “no”:      | a) grep -E "yes                                           | no" file |         |
| 133 | Show lines 10–20 only:                    | b) sed -n '10,20p' file                                   |          |         |
| 134 | Extract emails from file:                 | d) grep -E "[a-zA-Z0-9._%+-]+@[a-z0-9.-]+.[a-z]{2,}" file |          |         |
| 135 | awk print total & average of 3rd field:   | c) awk '{s+=$3} END{print s, s/NR}' file                  |          |         |

---

## 🧩 SECTION 9: Lab-style Command Output & Path Execution (Q136–150)

| #   | Question                                                            | Expected Output / Correct Command             |                                            |                                 |
| --- | ------------------------------------------------------------------- | --------------------------------------------- | ------------------------------------------ | ------------------------------- |
| 136 | `echo "hello world"                                                 | wc -w` →                                      | 2                                          |                                 |
| 137 | `echo "apple\nbanana\napple"                                        | sort                                          | uniq -c` →                                 | 2 apple, 1 banana (counts each) |
| 138 | `ls /bin/bash` →                                                    | /bin/bash                                     |                                            |                                 |
| 139 | Script `/scripts/runme.sh` not found; PATH missing `/scripts`. Fix? | export PATH=$PATH:/scripts                    |                                            |                                 |
| 140 | Given `#!/bin/bash` + `echo "Hi"` file, how to run?                 | chmod +x file; ./file                         |                                            |                                 |
| 141 | `grep "root" /etc/passwd                                            | wc -l` shows?                                 | Number of lines containing “root”          |                                 |
| 142 | `echo "A B C"                                                       | awk '{print $2}'` →                           | B                                          |                                 |
| 143 | `seq 1 3                                                            | while read n; do echo $((n*2)); done` →       | 2, 4, 6                                    |                                 |
| 144 | `touch file; [ -f file ] && echo yes` →                             | yes                                           |                                            |                                 |
| 145 | `x=5; if [ $x -gt 3 ]; then echo big; fi` →                         | big                                           |                                            |                                 |
| 146 | Script at `/usr/local/bin/clean.sh`, executable. Run from anywhere? | clean.sh                                      |                                            |                                 |
| 147 | `grep -i "bash" /etc/passwd                                         | cut -d: -f1` →                                | Usernames with bash shell                  |                                 |
| 148 | `awk -F: '{print $1,$7}' /etc/passwd                                | head -2` →                                    | Shows username and shell for first 2 users |                                 |
| 149 | `find / -name passwd 2>/dev/null` →                                 | Lists all files named passwd, suppress errors |                                            |                                 |
| 150 | `echo "mutu"                                                        | tee a.txt                                     | tr a-z A-Z` →                              | MUTU (and writes mutu to a.txt) |

---

✅ **Total Questions:** 150
✅ **Covers:** environment vars, customization, I/O redirection, bash scripts, PATH, loops, functions, regex, grep/sed/awk, lab outputs, execution commands
✅ **Answer key included inline**

---

Would you like me to turn this full set into a **printable quiz PDF** (with and without answers for practice)?
