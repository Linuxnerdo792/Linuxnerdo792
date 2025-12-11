Sure! Let’s focus on **bash conditional flags** like `-f`, `-d`, `-e`, etc., which are used in `if` statements to test files, directories, or other properties. I’ll first summarize the common ones with answers, then give 25 “what does this do?” style questions along with their answers.

---

### **Common Bash File Test Flags**

| Flag           | Meaning                                                            |
| -------------- | ------------------------------------------------------------------ |
| `-e filename`  | True if the file exists.                                           |
| `-f filename`  | True if the file exists **and is a regular file** (not directory). |
| `-d filename`  | True if the file exists **and is a directory**.                    |
| `-r filename`  | True if the file exists and is **readable**.                       |
| `-w filename`  | True if the file exists and is **writable**.                       |
| `-x filename`  | True if the file exists and is **executable**.                     |
| `-s filename`  | True if the file exists and **size > 0**.                          |
| `! expression` | Negates the test (true becomes false).                             |

---

### **25 Questions With Answers**

**Q1:** What does this check?

```bash
if [ -f myfile.txt ]; then echo "File exists"; fi
```

**A1:** Checks if `myfile.txt` exists and is a regular file.

**Q2:** What about this?

```bash
if [ -d myfolder ]; then echo "Directory exists"; fi
```

**A2:** Checks if `myfolder` exists and is a directory.

**Q3:**

```bash
if [ -e config.cfg ]; then echo "Exists"; fi
```

**A3:** True if `config.cfg` exists (file or directory).

**Q4:**

```bash
if [ -r secret.txt ]; then echo "Readable"; fi
```

**A4:** Checks if `secret.txt` exists and can be read.

**Q5:**

```bash
if [ -w log.txt ]; then echo "Writable"; fi
```

**A5:** Checks if `log.txt` exists and can be written to.

**Q6:**

```bash
if [ -x run.sh ]; then echo "Executable"; fi
```

**A6:** Checks if `run.sh` exists and is executable.

**Q7:**

```bash
if [ -s data.csv ]; then echo "Not empty"; fi
```

**A7:** Checks if `data.csv` exists and has a size greater than zero.

**Q8:**

```bash
if [ ! -f temp.txt ]; then echo "File missing"; fi
```

**A8:** True if `temp.txt` does **not** exist as a regular file.

**Q9:**

```bash
if [ -d /home ]; then echo "Home exists"; fi
```

**A9:** Checks if `/home` exists and is a directory.

**Q10:**

```bash
if [ -e /etc/passwd ]; then echo "Exists"; fi
```

**A10:** True if `/etc/passwd` exists.

**Q11:**

```bash
if [ -r notes.txt ] && [ -w notes.txt ]; then echo "Readable and writable"; fi
```

**A11:** True if `notes.txt` exists, readable, and writable.

**Q12:**

```bash
if [ -f myfile ] || [ -d myfile ]; then echo "Exists as file or dir"; fi
```

**A12:** True if `myfile` exists as either file or directory.

**Q13:**

```bash
if [ ! -d old ]; then echo "No old folder"; fi
```

**A13:** True if `old` does not exist as a directory.

**Q14:**

```bash
if [ -s report.log ]; then echo "Has content"; fi
```

**A14:** True if `report.log` exists and is not empty.

**Q15:**

```bash
if [ -x /usr/bin/python3 ]; then echo "Python executable exists"; fi
```

**A15:** Checks if `/usr/bin/python3` exists and is executable.

**Q16:**

```bash
if [ -w /tmp/file.txt ]; then echo "Can write"; fi
```

**A16:** True if `/tmp/file.txt` exists and is writable.

**Q17:**

```bash
if [ -r /etc/shadow ]; then echo "Readable"; fi
```

**A17:** Checks if `/etc/shadow` exists and is readable (usually root-only).

**Q18:**

```bash
if [ ! -e old.log ]; then echo "old.log missing"; fi
```

**A18:** True if `old.log` does not exist.

**Q19:**

```bash
if [ -f /var/log/syslog ]; then echo "Syslog is a file"; fi
```

**A19:** True if `/var/log/syslog` exists and is a regular file.

**Q20:**

```bash
if [ -d /var/log ]; then echo "Log folder exists"; fi
```

**A20:** True if `/var/log` exists and is a directory.

**Q21:**

```bash
if [ -s /tmp/output.txt ]; then echo "Not empty"; fi
```

**A21:** True if `/tmp/output.txt` exists and has content.

**Q22:**

```bash
if [ -x myscript.sh ] && [ -r myscript.sh ]; then echo "Can execute and read"; fi
```

**A22:** True if `myscript.sh` is readable and executable.

**Q23:**

```bash
if [ ! -w secret.txt ]; then echo "Cannot write"; fi
```

**A23:** True if `secret.txt` exists but is not writable.

**Q24:**

```bash
if [ -f a.txt ] || [ -d a.txt ]; then echo "Exists"; fi
```

**A24:** True if `a.txt` exists as a file or directory.

**Q25:**

```bash
if [ ! -s empty.txt ]; then echo "Empty file"; fi
```

**A25:** True if `empty.txt` exists and is empty (size 0) or does not exist.

---

If you want, I can **also make a second set with actual “what will be printed?” type snippet questions** that are trickier, mixing `-f`, `-d`, `-e`, and `!` in one-liners for a mini quiz.

Do you want me to make that next?
