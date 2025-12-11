# 🧭 Linux Path & Permission MCQs (30 Questions)

### **1.**
You are in `/home/research`. To run a script located in `/home/research/scripts/test.sh`, which command works if you are in `/home/research`?
- a) `test.sh`  
- b) `scripts/test.sh`  
- c) `./test.sh`  
- d) `/home/research/scripts/test.sh`

---

### **2.**
You are in `/usr/local/bin`, and a script `cleanup.sh` has permission `-rwxr-xr-x`. How do you run it from anywhere?
- a) `cleanup.sh`  
- b) `./cleanup.sh`  
- c) `/usr/local/bin/cleanup.sh`  
- d) `bash cleanup.sh`

---

### **3.**
A script `backup.sh` is located at `/opt/tools/backup.sh`. It’s executable. How do you execute it if `/opt/tools` is **not** in your `PATH`?
- a) `backup.sh`  
- b) `/opt/tools/backup.sh`  
- c) `bash backup.sh`  
- d) `tools/backup.sh`

---

### **4.**
You are in `/home/research/docs`. A file `run.sh` has `-rw-r--r--` permissions. What happens if you type `./run.sh`?
- a) It runs successfully  
- b) Permission denied  
- c) File not found  
- d) Syntax error

---

### **5.**
You are in `/usr/bin`, and you want to run the program `python3`. Which command correctly finds its absolute path?
- a) `locate python3`  
- b) `where python3`  
- c) `whereis python3`  
- d) `which python3`

---

### **6.**
You are in `/home/research/project`. Which of the following will execute `/home/research/project/start.sh` **within the current shell**?
- a) `bash start.sh`  
- b) `./start.sh`  
- c) `source start.sh`  
- d) `/home/research/project/start.sh`

---

### **7.**
You are in `/etc`. The command `pwd` prints `/etc`. Running `../bin/runme.sh` executes what?
- a) `/etc/bin/runme.sh`  
- b) `/bin/runme.sh`  
- c) `/usr/bin/runme.sh`  
- d) `bin/runme.sh`

---

### **8.**
A user has a script in `/usr/local/scripts/deploy.sh` with permission `-rwxr--r--`. Anyone can:
- a) Read, write, and execute  
- b) Read and execute  
- c) Only read  
- d) Owner can execute; others can’t

---

### **9.**
File: `/tmp/test.sh` has permission `-rw-r--r--`. To make it runnable, which command should you use?
- a) `chmod +r test.sh`  
- b) `chmod +x test.sh`  
- c) `chmod 777 test.sh`  
- d) `chmod +w test.sh`

---

### **10.**
You are in `/home/user/docs`. To execute `/home/user/scripts/hello.sh`, which command is **not** valid?
- a) `/home/user/scripts/hello.sh`  
- b) `bash /home/user/scripts/hello.sh`  
- c) `./scripts/hello.sh`  
- d) `source /home/user/scripts/hello.sh`

---

### **11.**
You want to run a script `/usr/bin/setup.sh` using its interpreter explicitly. Which command works?
- a) `/bin/bash /usr/bin/setup.sh`  
- b) `source /usr/bin/setup.sh`  
- c) `/usr/bin/setup.sh`  
- d) `./usr/bin/setup.sh`

---

### **12.**
A script `/home/alice/data.sh` starts with `#!/bin/bash`. What does this line mean?
- a) Runs with Bash shell  
- b) Must be sourced only  
- c) Must run as root  
- d) Runs only in `/bin`

---

### **13.**
File `program.sh` exists at `/usr/local/bin/program.sh`. If that path is in `PATH`, which command runs it directly?
- a) `program.sh`  
- b) `./program.sh`  
- c) `/usr/local/bin/program.sh`  
- d) `bash program.sh`

---

### **14.**
You are in `/home/user`. The script `/home/user/runme.sh` prints “Hello”. Which two commands output "Hello"?
- a) `bash runme.sh`  
- b) `./runme.sh`  
- c) `source runme.sh`  
- d) Both a and c

---

### **15.**
A binary `/bin/ls` has permission `-rwxr-xr-x`. Who can execute it?
- a) Only root  
- b) Owner only  
- c) Everyone  
- d) Nobody

---

### **16.**
You are in `/usr/local/bin` and want to see where `grep` is installed. Which command works?
- a) `where grep`  
- b) `whereis grep`  
- c) `which grep`  
- d) `find grep`

---

### **17.**
You want to add `/home/user/scripts` to your `PATH` permanently. Where should you edit?
- a) `/etc/passwd`  
- b) `~/.bashrc`  
- c) `/etc/shadow`  
- d) `/root/.bash_profile`

---

### **18.**
File `/opt/cleanup.sh` has permission `-rwx------`. Which user can execute it?
- a) Only owner  
- b) Only group  
- c) All users  
- d) Nobody

---

### **19.**
To execute a script `/tmp/a.sh` from **any** directory without typing full path, you must:
- a) Move it to `/usr/bin`  
- b) Add `/tmp` to PATH  
- c) Use `source /tmp/a.sh`  
- d) Copy to `/etc/rc.local`

---

### **20.**
You are in `/home/research`. Running `bash ../run.sh` executes which file?
- a) `/home/run.sh`  
- b) `/home/research/run.sh`  
- c) `/run.sh`  
- d) `../run.sh`

---

### **21.**
File `test.sh` is at `/home/user/test.sh` and PATH = `/usr/bin:/bin`. Running `test.sh` gives:
- a) File executes  
- b) File not found  
- c) Permission denied  
- d) Syntax error

---

### **22.**
You are in `/var/logs`. The command `../../usr/bin/python3` points to:
- a) `/usr/bin/python3`  
- b) `/var/usr/bin/python3`  
- c) `/logs/usr/bin/python3`  
- d) `/usr/local/bin/python3`

---

### **23.**
You are in `/etc`. The path `/home/user/project/run.sh` is given. To execute it:
- a) `run.sh`  
- b) `bash /home/user/project/run.sh`  
- c) `/etc/run.sh`  
- d) `cd /home/user/project && run.sh`

---

### **24.**
A file `/usr/local/bin/test.py` has no execute permission. You can still run it with:
- a) `python3 /usr/local/bin/test.py`  
- b) `./test.py`  
- c) `bash test.py`  
- d) `run test.py`

---

### **25.**
The command `echo $PATH` outputs `/usr/local/bin:/usr/bin:/bin`. This means:
- a) Scripts in these directories can be executed directly  
- b) Only `/usr/bin` programs run  
- c) You must use full path always  
- d) PATH is empty

---

### **26.**
A file `x.sh` is in `/home/user/scripts` but not executable. You run `bash x.sh`. It:
- a) Runs normally  
- b) Permission denied  
- c) Syntax error  
- d) File not found

---

### **27.**
A directory `/usr/local/bin` contains `script1`. You are in `/home/user`. To run it:
- a) `/usr/local/bin/script1`  
- b) `bash /usr/local/bin/script1`  
- c) `script1`  
- d) All of the above (if PATH includes `/usr/local/bin`)

---

### **28.**
You are in `/home/research/scripts`. To run a script in the parent directory:
- a) `../script.sh`  
- b) `./../script.sh`  
- c) `/home/research/script.sh`  
- d) All of the above

---

### **29.**
You want to execute `/etc/init.d/networking restart`. Which part specifies the **program name**?
- a) `/etc/init.d`  
- b) `networking`  
- c) `restart`  
- d) `/etc`

---

### **30.**
A script `demo.sh` has permission `-rwxrwx---`. The group members can:
- a) Execute only  
- b) Execute and write  
- c) Read and execute  
- d) Read, write, and execute

---

## ✅ **Answer Key**

1. b  
2. c  
3. b  
4. b  
5. d  
6. c  
7. b  
8. d  
9. b  
10. c  
11. a  
12. a  
13. a  
14. d  
15. c  
16. c  
17. b  
18. a  
19. b  
20. a  
21. b  
22. a  
23. b  
24. a  
25. a  
26. a  
27. d  
28. d  
29. b  
30. d  
