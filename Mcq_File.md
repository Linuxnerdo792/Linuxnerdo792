Perfect 🔥 Research — here come **50 challenging, high-concept MCQs** (mix of tricky logic, command behavior, permission puzzles, and conceptual traps) from your “Files, Directories, and OS Structure” topic.

These are **Level: Hard+Interview+Exam tricky** — perfect to test deep understanding.
👉 Answers (with explanation) are given at the end.

---

## 🧩 50 Advanced MCQ – Files, Directories & Permissions

---

### 🧠 Filesystem Structure (Q1–10)

1. Which of the following directories in Linux contains essential binaries needed to boot the system?
   a) /usr/bin
   b) /bin
   c) /opt/bin
   d) /etc/bin

2. Which directory holds user mailboxes in traditional Linux systems?
   a) /mail
   b) /home/mail
   c) /var/mail
   d) /usr/mail

3. In Linux, `/proc` is:
   a) A real directory containing running process logs
   b) A virtual filesystem showing process and kernel information
   c) A backup directory for daemons
   d) A mount point for user programs

4. What is the function of `/dev/null`?
   a) Stores error logs
   b) Deletes files automatically
   c) Discards data written to it
   d) Stores kernel dumps

5. Which of the following correctly represents the full path of the root user’s home directory?
   a) /home/root
   b) /etc/root
   c) /root
   d) /usr/root

6. In macOS, the `/Applications` directory is equivalent to what in Windows?
   a) C:\System32
   b) C:\Program Files
   c) C:\Users
   d) C:\Windows

7. What is mounted at `/` in a Linux system?
   a) Bootloader
   b) The entire filesystem hierarchy root
   c) The kernel image
   d) System libraries only

8. Which of the following directories contains device files?
   a) /etc
   b) /usr
   c) /dev
   d) /mnt

9. Which directory in Linux is most likely to contain temporary files that are cleared on reboot?
   a) /tmp
   b) /var
   c) /opt/tmp
   d) /usr/tmp

10. Which command shows the type of filesystem used on mounted devices?
    a) df -T
    b) mount -f
    c) du -f
    d) lsblk -x

---

### 🧩 File Operations & Commands (Q11–20)

11. What does the command `cp -r dir1 dir2` do?
    a) Copies dir1 into dir2 recursively
    b) Copies contents of dir2 into dir1
    c) Removes dir1 after copying
    d) Only copies files, not subdirectories

12. What does the command `mv file1 file2 dir/` do if `dir` exists?
    a) Moves both files into dir
    b) Renames dir to file1
    c) Overwrites dir with file2
    d) Fails with an error

13. Which command combination creates a new file if it doesn’t exist and updates its timestamp if it does?
    a) nano
    b) cat
    c) touch
    d) echo

14. What happens if you run `rm -rf /` as root?
    a) Deletes user directory
    b) Deletes all files on system recursively (potentially catastrophic)
    c) Only removes /tmp files
    d) Nothing happens

15. The command `ln file1 file2` creates:
    a) A symbolic link
    b) A hard link
    c) A shortcut like in Windows
    d) A backup

16. Which command is used to search for files in a directory hierarchy?
    a) locate
    b) find
    c) search
    d) grep

17. The command `cat > notes.txt` followed by typing text will:
    a) Append text to notes.txt
    b) Overwrite notes.txt
    c) Display notes.txt
    d) Create symbolic link

18. What does `head -n 5 file.txt` do?
    a) Prints last 5 lines
    b) Prints 5 lines per page
    c) Prints first 5 lines
    d) Deletes 5 lines

19. The command `less file.txt` is better than `cat file.txt` because:
    a) `less` edits the file
    b) `less` supports paging and navigation
    c) `less` loads entire file into RAM
    d) `less` compresses output

20. What does `rm -i` do?
    a) Deletes without prompt
    b) Deletes with confirmation for each file
    c) Deletes directories only
    d) Ignores hidden files

---

### 🔐 Permissions & Ownership (Q21–35)

21. In Linux, who can change file permissions?
    a) Only the file owner and root
    b) Any user
    c) Only system group members
    d) Only admins with sudo

22. What is the symbolic permission equivalent of 764?
    a) rwxr--rw-
    b) rwxrw-r--
    c) rwxrw-r--
    d) rwxrw-r-- (trick question – look closely 👀)

23. Which command assigns both a new owner and a new group to a file?
    a) chmod
    b) chgrp
    c) chown
    d) lsattr

24. What is the purpose of the “sticky bit” on a directory (e.g., `/tmp`)?
    a) Makes directory hidden
    b) Only owner of a file can delete it
    c) Prevents modification
    d) Allows group write access

25. A file shows permission `-rwxr-xr--`. Who can execute it?
    a) Owner only
    b) Owner and group
    c) Owner and group, not others
    d) Everyone

26. Which command removes all permissions from “other” users on file `secret.txt`?
    a) chmod o-rwx secret.txt
    b) chmod 000 secret.txt
    c) chmod ugo-rwx secret.txt
    d) chown o-rwx secret.txt

27. What permission value allows full access to owner and read/execute to others?
    a) 744
    b) 755
    c) 766
    d) 700

28. Which command recursively changes ownership of a directory and its contents?
    a) chown -r
    b) chown -R
    c) chmod -r
    d) chgrp -r

29. To add execute permission for the group only, you’d use:
    a) chmod g+x file
    b) chmod +x file
    c) chmod a+x file
    d) chmod 111 file

30. What does `umask` do?
    a) Sets default file permission restrictions
    b) Unmasks hidden files
    c) Locks files for root
    d) Displays only system users

31. Which file stores user account information?
    a) /etc/shadow
    b) /etc/users
    c) /etc/passwd
    d) /home/.users

32. What is stored in `/etc/shadow`?
    a) Encrypted passwords and aging info
    b) Usernames only
    c) Group memberships
    d) File permissions

33. Which command lists all groups a specific user belongs to?
    a) whoami
    b) groups username
    c) id username
    d) Both b and c

34. What is the effect of `chmod 4755 file`?
    a) Adds sticky bit
    b) Sets SUID bit — executes as owner
    c) Sets SGID
    d) No effect

35. Which command changes only the group owner of a file?
    a) chgrp
    b) chmod
    c) chown
    d) sudo

---

### 🧍 User, Group & Root (Q36–45)

36. Which command creates a new user and home directory in most Linux systems?
    a) useradd
    b) adduser
    c) createuser
    d) mkuser

37. What is `/etc/skel` used for?
    a) Skeleton directory for new users’ home setup
    b) Stores deleted users
    c) Backup passwords
    d) User groups info

38. The default shell for new users is set in:
    a) /etc/bashrc
    b) /etc/passwd
    c) /etc/default/useradd
    d) /etc/sudoers

39. What is the UID of the root user?
    a) 0
    b) 1
    c) 100
    d) 500

40. Which command safely edits the sudoers file?
    a) vim /etc/sudoers
    b) nano /etc/sudoers
    c) visudo
    d) edit /sudoers

41. What happens if `/etc/sudoers` file is edited manually and has syntax errors?
    a) Nothing changes
    b) Sudo stops working completely
    c) Root password resets
    d) System locks users out permanently

42. Which group must a user be in to execute sudo by default (on Debian/Ubuntu)?
    a) root
    b) admin
    c) wheel
    d) sudo

43. What does `sudo !!` do?
    a) Repeats last command as root
    b) Displays last sudo command
    c) Cancels current sudo session
    d) Shows sudo history

44. Which command deletes a user and their home directory?
    a) userdel -r username
    b) deluser username
    c) rm -r /home/username
    d) userdel username

45. Which command locks a user account (preventing login)?
    a) passwd -d
    b) passwd -l
    c) chown -l
    d) usermod -l

---

### ⚙️ Tricky Behavior & Conceptual (Q46–50)

46. Which of these commands **will not** delete a directory?
    a) rm -rf dirname
    b) rmdir dirname
    c) rm dirname
    d) rm -r dirname

47. If you `cp -p file1 file2`, what does `-p` preserve?
    a) File owner, permissions, and timestamps
    b) Only content
    c) Only size
    d) Permissions only

48. A user has permissions `r--` on a directory. Can they view filenames?
    a) Yes, they can list
    b) No, they need execute permission to access contents
    c) Only if they’re root
    d) Yes, if umask allows

49. Which filesystem supports case-insensitive filenames by default?
    a) ext4
    b) NTFS
    c) XFS
    d) Btrfs

50. Which command lists all mounted filesystems?
    a) mount
    b) cat /proc/mounts
    c) df -h
    d) All of the above

---

## ✅ ANSWER KEY WITH EXPLANATION

| #  | Ans | Explanation                                |
| -- | --- | ------------------------------------------ |
| 1  | b   | `/bin` holds essential binaries            |
| 2  | c   | User mailboxes in `/var/mail`              |
| 3  | b   | Virtual filesystem for kernel/process info |
| 4  | c   | “Black hole” — data sink                   |
| 5  | c   | Root’s home is `/root`                     |
| 6  | b   | `/Applications` ≈ Program Files            |
| 7  | b   | Root of entire filesystem                  |
| 8  | c   | `/dev` = device files                      |
| 9  | a   | `/tmp` cleared on reboot                   |
| 10 | a   | `df -T` shows type                         |
| 11 | a   | Copies recursively                         |
| 12 | a   | Moves both files into `dir`                |
| 13 | c   | `touch` creates or updates timestamp       |
| 14 | b   | Wipes entire system                        |
| 15 | b   | Hard link                                  |
| 16 | b   | `find` searches                            |
| 17 | b   | Overwrites file                            |
| 18 | c   | First 5 lines                              |
| 19 | b   | Paging navigation                          |
| 20 | b   | Interactive delete prompt                  |
| 21 | a   | Owner or root only                         |
| 22 | a   | 7=rw,6=rw,4=r → rwxrw-r--                  |
| 23 | c   | `chown user:group file`                    |
| 24 | b   | Sticky bit restricts delete                |
| 25 | b   | Owner+group execute                        |
| 26 | a   | Removes “other” permissions                |
| 27 | b   | rwx (7) r-x (5) r-x (5)                    |
| 28 | b   | `-R` = recursive                           |
| 29 | a   | Add execute for group                      |
| 30 | a   | Controls default mask                      |
| 31 | c   | `/etc/passwd` user info                    |
| 32 | a   | Encrypted password file                    |
| 33 | d   | Both valid                                 |
| 34 | b   | SUID bit                                   |
| 35 | a   | `chgrp` modifies group only                |
| 36 | b   | `adduser` adds & configures                |
| 37 | a   | Template directory                         |
| 38 | c   | Default shell setting                      |
| 39 | a   | Root UID = 0                               |
| 40 | c   | `visudo` checks syntax                     |
| 41 | b   | sudo fails if syntax error                 |
| 42 | d   | `sudo` group (Ubuntu)                      |
| 43 | a   | Runs last command as root                  |
| 44 | a   | `userdel -r` removes home                  |
| 45 | b   | Locks password login                       |
| 46 | c   | `rm` alone fails for dirs                  |
| 47 | a   | Preserves metadata                         |
| 48 | b   | Need “x” to access directory               |
| 49 | b   | NTFS is case-insensitive                   |
| 50 | d   | All can show mounts                        |

---

Would you like me to now make a **simulated Linux practical quiz** (where I describe a terminal scenario and you choose the correct command or output)? That’s the next-level prep used in OS labs and internships 🔥
