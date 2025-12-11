Got it. Let's break this down step by step. I’ll give a clear explanation for each concept, how to set things up (like aliases), and then generate conceptual questions with explanations. I’ll keep it structured so it’s easy to follow.

---

## **1. Environment Variables**

Environment variables store configuration values used by the system or applications.

* **Common variables:**

  * `HOME` → your home directory
  * `USER` → current username
  * `SHELL` → default shell (e.g., `/bin/bash`)
  * `PATH` → directories where executables are searched

* **Check variable values:**

```bash
echo $HOME
echo $USER
echo $SHELL
echo $PATH
```

* **Set a variable temporarily (session only):**

```bash
MY_VAR="Hello"
echo $MY_VAR
```

* **Set a variable permanently:** Add it to `.bashrc` or `.profile`

```bash
echo 'export MY_VAR="Hello"' >> ~/.bashrc
source ~/.bashrc
```

---

## **2. Aliases & Customizations**

Aliases are shortcuts for commands.

* **Set an alias temporarily:**

```bash
alias ll='ls -al'
```

* **Set alias permanently:** Add to `.bashrc`

```bash
echo "alias ll='ls -al'" >> ~/.bashrc
source ~/.bashrc
```

* **Remove an alias temporarily:**

```bash
unalias ll
```

* **View all aliases:**

```bash
alias
```

---

## **3. Useful Commands**

| Command   | Usage                          |
| --------- | ------------------------------ |
| `diff`    | Compare files line by line     |
| `find`    | Search for files/directories   |
| `file`    | Determine file type            |
| `wc`      | Count words, lines, bytes      |
| `sort`    | Sort lines in files            |
| `uniq`    | Remove duplicate lines         |
| `whereis` | Locate binary/source/man files |
| `which`   | Show path of executable        |

**Examples:**

```bash
diff file1.txt file2.txt
find /home -name "*.txt"
file script.sh
wc -l file.txt
sort names.txt | uniq
whereis bash
which python3
```

---

## **4. IO Streams & Redirection**

* **Standard input (stdin)** → 0
* **Standard output (stdout)** → 1
* **Standard error (stderr)** → 2

**Redirection:**

```bash
# Redirect stdout to file
echo "Hello" > file.txt

# Append stdout to file
echo "World" >> file.txt

# Redirect stderr
ls /nonexistent 2> error.txt

# Redirect both stdout and stderr
ls /nonexistent &> alloutput.txt

# Pipe stdout to another command
cat file.txt | sort

# Use tee to write to file AND display output
cat file.txt | tee output.txt
```

---

## **5. Executing Scripts**

* **Run in current shell (source or .):**

```bash
source script.sh
. script.sh
```

* **Run by specifying interpreter:**

```bash
bash script.sh
```

* **Run with `#!` and execute permissions:**

```bash
#!/bin/bash
echo "Hello"
chmod +x script.sh
./script.sh
```

* **Run from anywhere:** Add the script’s path to `PATH`

```bash
export PATH=$PATH:/home/user/scripts
./myscript.sh
```

---

## **6. Setting Up an Alias Step by Step**

1. Open terminal.
2. Open `.bashrc` in an editor:

```bash
nano ~/.bashrc
```

3. Add your alias at the end:

```bash
alias gs='git status'
```

4. Save and exit.
5. Apply changes:

```bash
source ~/.bashrc
```

6. Test:

```bash
gs
```

---

## **Conceptual Questions (10 per topic)**

### **Environment Variables**

1. What does `$HOME` represent and how is it used in scripts?
   *Answer:* `$HOME` is the user’s home directory. Scripts can use it to refer to the user’s files without hardcoding paths.

2. How can you make a variable available to all child processes?
   *Answer:* Use `export VAR=value`.

3. Difference between `~` and `$HOME`?
   *Answer:* Both point to the home directory, but `~` is shell shorthand, `$HOME` is an environment variable.

4. What happens if you modify `PATH` incorrectly?
   *Answer:* Commands may fail because the shell cannot find executables.

5. How can you view all environment variables?
   *Answer:* `printenv` or `env`.

6. Difference between `.bashrc` and `.profile`?
   *Answer:* `.bashrc` runs for interactive non-login shells; `.profile` runs for login shells.

7. Can a variable be both local and exported?
   *Answer:* Yes, local to shell first, then exported to child processes.

8. How to temporarily override `PATH` for a command?
   *Answer:* `PATH=/tmp:$PATH command`

9. Why use environment variables in scripts?
   *Answer:* To make scripts portable and configurable.

10. How to unset an environment variable?
    *Answer:* `unset VAR_NAME`

---

### **Aliases & Customizations**

1. How to create an alias for `ls -alh`?
   *Answer:* `alias ll='ls -alh'`

2. How to make an alias permanent?
   *Answer:* Add it to `.bashrc` and `source ~/.bashrc`.

3. Difference between alias and function in bash?
   *Answer:* Alias is a simple shortcut; function can take parameters and have complex logic.

4. How to remove a temporary alias?
   *Answer:* `unalias alias_name`

5. Why should aliases be defined in `.bashrc` and not `.profile`?
   *Answer:* `.bashrc` runs for interactive shells where aliases are needed.

6. Can aliases be used in scripts?
   *Answer:* Not directly unless the script is sourced.

7. How to list all aliases?
   *Answer:* `alias`

8. Can alias override existing commands?
   *Answer:* Yes, e.g., `alias rm='rm -i'`

9. How to prevent an alias from being used temporarily?
   *Answer:* Use `\command` or `command` before the command name.

10. Why use aliases instead of full commands?
    *Answer:* For convenience, speed, and avoiding mistakes.

---

### **IO Streams & Redirection**

1. What is the difference between stdout and stderr?
   *Answer:* stdout is normal output, stderr is for errors.

2. How to redirect stderr to a file?
   *Answer:* `command 2> error.txt`

3. How to redirect both stdout and stderr to the same file?
   *Answer:* `command &> file.txt`

4. What does `|` do in bash?
   *Answer:* Pipes stdout of one command to stdin of another.

5. Difference between `>` and `>>`?
   *Answer:* `>` overwrites, `>>` appends.

6. How does `tee` differ from `>`?
   *Answer:* `tee` writes to file and stdout simultaneously.

7. What is stdin?
   *Answer:* Standard input stream, usually keyboard.

8. How to redirect stdin from a file?
   *Answer:* `command < input.txt`

9. What happens if you redirect stderr to stdout?
   *Answer:* `command 2>&1` merges errors into normal output.

10. Why separate stderr and stdout?
    *Answer:* To handle errors differently from normal output.

---

I can continue with **Commands, Executing Scripts, and Generating 10 Questions per topic with answers**, if you want me to do that next.

Do you want me to continue with that?
