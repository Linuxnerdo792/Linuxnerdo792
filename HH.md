Perfect ❤️ — I got you, Research!

Here’s **Lab 06 (Dotfile Installer Script)** broken into **50 quizzes** covering **every single concept** — from *easy recall* to *deep Bash scripting and getopts logic*.
Each question includes an **answer key** (after “→”) so you can study fast and efficiently before your CEG 2350 evaluation or midterm.

---

# 🧠 **Lab 06 – Dotfile Installer Script | 50 Quiz Questions (With Answers)**

---

## 🟢 **Part 1: Bash Aliases (Basic)**

**1.** What is a Bash alias used for?
→ To create shortcuts for longer or frequently used commands.

**2.** In which file can user-specific aliases be stored permanently?
→ `~/.bash_aliases`

**3.** What command do you use to make an alias permanent after editing `.bash_aliases`?
→ `source ~/.bashrc`

**4.** What is the difference between `.bashrc` and `.bash_aliases`?
→ `.bashrc` runs on shell startup; `.bash_aliases` stores aliases and is sourced by `.bashrc`.

**5.** Where do you typically find the code snippet that enables `.bash_aliases` in `.bashrc`?
→ Near the end of `.bashrc`, often commented with “Enable bash aliases if present”.

**6.** What does this code snippet in `.bashrc` do?

```bash
if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi
```

→ It checks if `.bash_aliases` exists and sources it if it does.

**7.** How would you create an alias called `moo` that displays a fortune from cowsay?
→ `alias moo='fortune | cowsay -f tux'`

**8.** What does the command `curl wttr.in` do?
→ It shows a weather report in the terminal.

**9.** What is the purpose of `lolcat` in the terminal?
→ To add rainbow colors to text output.

**10.** Which directory symbol represents a user’s home directory?
→ `~`

---

## 🟡 **Part 2: Dotfile Installer Script (Core Logic)**

**11.** What should the filename of the main script be for this lab?
→ `dotinstall`

**12.** What function should display usage instructions?
→ `printHelp`

**13.** What Bash command is used to parse options like `-s`, `-a`, etc.?
→ `getopts`

**14.** What does `OPTARG` represent in getopts?
→ The argument value associated with an option.

**15.** What is the purpose of `case` statements in a getopts loop?
→ To handle actions for each command-line option.

**16.** What does `-h` option do in the script?
→ Calls `printHelp` and exits.

**17.** What does the `-s` option do?
→ Creates a symbolic link from `.bash_aliases` in `Lab06` to the user’s home directory.

**18.** What command is used to create symbolic links in Linux?
→ `ln -s`

**19.** What should happen if `.bash_aliases` already exists when `-s` is used?
→ Prompt the user before overwriting it.

**20.** What does the `-d` option do?
→ Removes the symbolic link in the user’s home directory.

**21.** What should the `-a` option do?
→ Appends a new alias string to `.bash_aliases`.

**22.** What should the `-r` option do?
→ Removes a specific alias by name from `.bash_aliases`.

**23.** What should happen if `-r` can’t find the alias name?
→ Notify the user that no matching alias was found.

**24.** What should the script display if an unsupported option is given?
→ “Option not supported” followed by usage info.

**25.** Which option string in getopts includes support for all flags in this lab?
→ `:hs:da:r:`

---

## 🟠 **Part 2: Intermediate Understanding (getopts & Behavior)**

**26.** What type of error occurs if an option is used but missing an argument?
→ getopts might misinterpret the next option as an argument.

**27.** What is a possible fix for detecting a missing argument in getopts?
→ Check if a variable (e.g., `$OPTARG`) is empty before use.

**28.** What should happen if `bash dotinstall -z` is run?
→ Script shows usage message (invalid option).

**29.** How do you make a file executable in Linux?
→ `chmod +x filename`

**30.** What happens when you run `bash dotinstall -h`?
→ It prints the usage guide with all supported options.

**31.** What message should appear after creating a symbolic link successfully?
→ “Creating symbolic link in /home/ubuntu named .bash_aliases”

**32.** What command reloads the shell to apply alias changes?
→ `source ~/.bashrc`

**33.** How should commits be structured for this lab?
→ At least 3 commits showing incremental progress.

**34.** What should each commit message describe?
→ What was added or tested successfully at that stage.

**35.** What is the minimum number of commits required?
→ Three (3).

---

## 🔵 **Part 3: Retrospective (Conceptual + Reflection)**

**36.** In simple terms, what is `getopts`?
→ A Bash built-in for parsing short command-line options.

**37.** What is the main benefit of using `getopts` over manual argument handling?
→ It provides structured option parsing with built-in error handling.

**38.** If you got stuck debugging your script, what would you include in the README?
→ A note on what failed, what caused it, and how it was fixed.

**39.** What is one improvement feature idea for `dotinstall`?
→ Prevent adding duplicate aliases or prompt before overwrite.

**40.** What Linux command is used to check if a file exists before creating a link?
→ `[ -f filename ]`

---

## 🟣 **Part 4: Usage Guide (Documentation & Output)**

**41.** What should the Usage Guide describe?
→ Purpose of script, alias contents, and example commands.

**42.** What should be included in `.bash_aliases` in your repo?
→ The actual aliases you created for Part 1.

**43.** Give one example of a command and its output from the script.
→ `$ bash dotinstall -r ls` → “Alias for ls removed from .bash_aliases”.

**44.** What file must exist in the GitHub repo for full credit?
→ `README.md`, `dotinstall`, and `.bash_aliases`.

**45.** What should the README file use for formatting?
→ Markdown (`.md`) syntax.

---

## 🔴 **Extra Credit + Advanced Bash Logic (Very Hard)**

**46.** How could you verify an alias before appending it to `.bash_aliases`?
→ Test-run the alias command; if it executes without error, append it.

**47.** How could your script detect if an alias name already exists?
→ Use `grep -q "alias name=" .bash_aliases`

**48.** How could you safely remove one of multiple aliases with similar names?
→ Prompt the user to confirm or pick the correct alias.

**49.** What happens if the script is run without any options?
→ It should detect the missing options and print help info.

**50.** Why should you document mistakes or corrections in this lab?
→ Helps with debugging, improves understanding, and earns full rubric marks.

---

Would you like me to make a **printable study sheet (PDF)** version next — with **sections, answer spacing, and checkboxes** for self-testing before submission or exam prep?
I can make it beautifully formatted with headings like
**“Part 1: Aliases” → “Part 2: getopts Script” → “Part 3: Reflection” → “Part 4: Documentation.”**
