Sure! Here's a **complete set of the 20 questions with detailed answers and explanations** based on your `getopts` script:

---

### 1. What will be printed if the script is run with:

```bash
./script.sh -n bob -a 60
```

**Answer:**

```
bob
bubbles
```

**Explanation:** `-n bob` assigns `"bob"` to variable `a` and it is printed first. `-a 60` assigns `60` to `b`, which is greater than 55, so `"bubbles"` is printed.

---

### 2. Which variable stores the value provided to the `-n` option?

**Answer:** `a`
**Explanation:** In the `case` statement, `n)` assigns `$OPTARG` to `a`.

---

### 3. Which variable stores the value provided to the `-a` option?

**Answer:** `b`
**Explanation:** In the `case` statement, `a)` assigns `$OPTARG` to `b`.

---

### 4. What will be printed if the script is run as:

```bash
./script.sh -a 30 -n alice
```

**Answer:**

```
alice
b
```

**Explanation:** `a = alice` and `b = 30`. Since `30` is not greater than 55, the script prints `"b"`. Order of flags does not affect parsing.

---

### 5. What happens if you run the script with no options at all?

**Answer:**

```

b
```

**Explanation:** Both `a` and `b` are empty strings. Printing `$a` outputs nothing. Comparison `[[ $b -gt 55 ]]` treats empty as 0, which is not greater than 55, so `"b"` prints.

---

### 6. What happens if you run the script with an unknown option, like `-x`?

**Answer:** Prints usage message:

```
Usage: ./script.sh [-n a] [-a b]
```

**Explanation:** `\?` in the `case` statement catches invalid options and exits with code 1.

---

### 7. If you run:

```bash
./script.sh -n test -a 55
```

**Answer:**

```
test
b
```

**Explanation:** `b = 55` is **not greater than 55**, so the else branch prints `"b"`.

---

### 8. Why does the script use `"$OPTARG"` inside the `case` statement?

**Answer:** `$OPTARG` holds the argument passed to the current option.
**Explanation:** Quotes prevent word splitting or errors if the argument contains spaces.

---

### 9. What is the purpose of `\?` in the `case` statement?

**Answer:** To catch invalid or unknown options.
**Explanation:** If the user provides a flag not defined in `"n:a:"`, it prints the usage message and exits.

---

### 10. How could the script fail if you pass a non-numeric value to `-a`, like:

```bash
./script.sh -n bob -a hello
```

**Answer:** Bash will give an error:

```
bash: [[: hello: integer expression expected
```

**Explanation:** The conditional `[[ $b -gt 55 ]]` expects a numeric value; a string causes a comparison error.

---

### 11. If you reverse the flags order:

```bash
./script.sh -a 70 -n bob
```

**Answer:**

```
bob
bubbles
```

**Explanation:** `getopts` correctly parses options regardless of order. Output remains the same.

---

### 12. What type of comparison is being used in:

```bash
if [[ $b -gt 55 ]]; then
```

**Answer:** Numeric comparison.
**Explanation:** `-gt` stands for “greater than” for integers in bash.

---

### 13. Explain the difference between `-gt` and `>` in bash.

**Answer:**

* `-gt` → numeric comparison
* `>` → string comparison or redirection operator

**Explanation:** For numbers, always use `-gt`, `-lt`, `-eq`. Using `>` for numbers compares ASCII values, which can give wrong results.

---

### 14. How would you modify the script to also print `"small"` if `b < 30`?

**Answer:**

```bash
if [[ $b -gt 55 ]]; then
    echo "bubbles"
elif [[ $b -lt 30 ]]; then
    echo "small"
else
    echo "b"
fi
```

**Explanation:** Adds a new conditional branch for values below 30.

---

### 15. If you remove the `echo "$a"` line, what effect does it have on the output?

**Answer:** Only `"b"` or `"bubbles"` will print; the `-n` value is not displayed.

---

### 16. What will happen if you accidentally swap the variables inside the `case` assignments?

**Answer:** Flags will assign values to the wrong variables, producing unexpected output.

**Example:** `-n` assigns to `b` and `-a` assigns to `a`. Output logic may fail.

---

### 17. Explain why using double quotes around variables is important in bash (`"$a"` vs `$a`).

**Answer:** Prevents word splitting and errors if variable is empty or contains spaces.

**Example:** Without quotes, `[[ $a -gt 55 ]]` could throw an error if `$a` is empty.

---

### 18. What would happen if you used `getopts "n:a"` (missing colon after `a`)?

**Answer:** `-a` would no longer expect an argument. Passing an argument could cause unexpected behavior.

---

### 19. How would the script behave if multiple `-n` or `-a` options are provided?

**Answer:** Only the last occurrence of each option is stored; previous ones are overwritten.

**Example:**

```bash
./script.sh -n one -n two -a 60
```

`a = two`, `b = 60`.

---

### 20. Explain what `exit 1` does in the script and why it is used.

**Answer:** Exits the script with status code 1, indicating an error.

**Explanation:** Used when the user provides an invalid option to stop the script instead of running further with wrong input.

---

If you want, I can **also make a table showing all example `./script.sh` commands and their exact outputs**—this makes exam prep much faster.

Do you want me to make that table?
