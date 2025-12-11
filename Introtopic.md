**Everything from week one and Lab one**

**Terminal**

>A program that provides a user interface to interact with a computer system through text-based input and output.GNOME Terminal, macOS Terminal, Windows Terminal

**Console**

>A physical or virtual device that allows users to interact with a computer system, often providing a combination of text-basedinput and output.Command Prompt (cmd.exe), PowerShell, Linux virtual terminals (e.g., TTYs)

```
Shell
 A command interpreter program that enables users to interact withan operating system, executing commands and scripts. Bash, PowerShell, Zsh, Csh, Ksh
```
```
Secure Shell (SSH)
 cryptographic network protocol for operating network services securelyover an unsecured network.
 Typical applications include remote command-line, login, and remote command execution, but any network service can be secured with SSH.
 Think secure communication between shells
 Remote Desktop Protocol (RDP)
 proprietary protocol developed by Microsoft which provides a user with
a graphical interface to connect to another computer over a network
connection.
 The user employs RDP client software for this purpose, while the other
computer must run RDP server software

Directories / Folders
 Keeps the association of name(s) and location of content(s)
 Names of files and corresponding I-nodes
 Every directory has a parent directory it belongs to
 The top level directory is parent of itself
 In a directory, if you run "ls –lah", you'll see two listings with dots
 "." is a reference to itself
 ".." is a reference to it's parent
```

```
* Vs .
 * - a wildcard pattern matcher
 /etc/*-release will match anything that ends in “-release” in /etc/
 . – think “this directory right here”
 “git add .”– add anything in this directory
 .. – think “the directory before”
```

```
Absolute vs Relative Path
 Relative is relative to where you are
 Can still be a path, though
 class-examples/my_file.txt
 file_open(my_file);
 Absolute is the full directory path, no shortcuts
 /home/ubuntu/class-examples/my_file.txt
 file_open(C:\Users\kduncan\Documents\data\my_file.txt)

```

```
Make a folder named demo
 Go into the demo folder
 Create two files. In one file, add a list of your favorite things
 Move your file with your list to your user’s home directory
 Make your file with your list a hidden file
 Delete the demo folder
 cd touch mkdir vim pwd ls clear
 Need: mv rm
 To exit vim: escape :wq
```
```
Here is one way to do each step using common Linux commands in the terminal.[1][2][3]

## Step‑by‑step commands

1. Make a folder named `demo`  
   - Command:  
     `mkdir demo`[1]

2. Go into the `demo` folder  
   - Command:  
     `cd demo`[2][4]

3. Create two files  
   - Commands (example names):  
     `touch list.txt other.txt`[3][1]

4. In one file, add a list of your favorite things (using vim)  
   - Open the file in vim:  
     `vim list.txt`  
   - In vim:  
     - Press `i` to enter insert mode.[5][6]
     - Type your list (one item per line if you like).  
     - Press `Esc` to leave insert mode.[6][5]
     - Type `:wq` and press Enter to save and quit.[7][5][6]

5. Move your file with your list to your user’s home directory  
   - From inside `demo` (check with `pwd` if needed):  
     `mv list.txt ~`[8][3]

6. Make your file with your list a hidden file (in your home directory)  
   - Change to home directory:  
     `cd ~`[9][3]
   - Rename it so it starts with a dot:  
     `mv list.txt .list.txt`[3][8]
   - Now `.list.txt` is hidden in normal `ls` output; use `ls -a` to see it.[10][3]

7. Delete the `demo` folder  
   - Go to the directory that contains `demo` (for example your home):  
     `cd ~`  
   - Remove the folder and its contents:  
     `rm -r demo`[11][1]

8. Helpful extra commands mentioned  
   - `pwd` – show current directory.[4][9]
   - `ls` – list files (add `-a` to see hidden).[8][1]
   - `clear` – clear the terminal screen.[11][1]
```
```
File Permissions: Linux
 Run "ls –lah" in a directory with a file in it
 There are four "chunks"
 Starts with "d" - is a directory
 Starts with "-" - is a file
 Starts with something else? Google it.
 Next three spots define "user" permission
 Each spot defines if read [r], write [w], and execute [x] are set
 Next three define "group" permissions
 Final three define "other" permissions
 Next, it tells you who owns the file, and to which group it belongs
```
```
 _ | _ _ _ | _ _ _ | _ _ _
 owner group other
 rwx
 R = read = 4
 W = write = 2
 X = execute = 1
 4 0/1_ 2 0/1_ _1 0/1
 $ chmod 600 filename
```
```
$ chmod 600 key_name.pem
 Think of the numerics as 6 0 0
 6 = user permissions to read & write
 0 = group permissions to get nothing (no rwx)
 0 = other permissions to get nothing (no rwx)
 0 = no one in this tier gets anything (no rwx)
 1 = execute
 2 = write
 3 = write + execute
 4 = read
 5 = read + execute
 6 = read + write
 7 = read + write + execute
```

```
 adduser new_username
 Creates user, has you give them a password, creates their home
directory
 $ chown username file_or_folder_name
 Change the owner of a file or folder
 $ addgroup new_groupname
 Create a new group
 Checkout /etc/group - this is where you add groupies to groups
 $ chgrp groupname file_or_folder_name
 Change the group of a file or folder
```

```
Who are you? Who who
 $ whoami
 Returns the username you are currently using
 $ sudo whoami
 $ id
 Returns all the groups you are a member of
 $ id userName
 $ group
 Returns groups you are a member of
 $ getent group groupName
 Returns members of a given groupName
Passwords and a nod to PAM
 PAM = Pluggable Authenticaton Module
 Linux systems use PAM by default, you can add other types of
authentication
 LDAP, Active Directory, etc.
 PAM looks in some spots:
 /etc/passwd
 If the account is locally made, there will be a listing here
 Can set if the given user can log in. Why does that matter?
 /etc/shadow
 Passwords are not stored as plain text anymore
Messing with Groups
 # addgroup groupname
 /etc/groups
 This is also where you go to add users to the sudo group
 $ chgrp newgroupname fileorfolder
Messing with sudo
 $ sudo su
 Runs programs as the root user
 “built ins” like cd need additional workarounds
 `su root` OR `sudo –s` and then run your command
 The ubuntu account has passwordless sudo
 /etc/sudoers
 Where sudo configs go. Based on username or group I can define what
commands they can run as sudo
 https://www.digitalocean.com/community/tutorials/how-to-edit-thesudoers-file
 $ sudo su username
 $ su username - prompts for the password of the username
 Pay attention to where you are - $ pwd
Linux Resources
 Managing users & groups
 https://www.redhat.com/sysadmin/linux-user-group-management
 Understanding /etc/password
 https://linuxize.com/post/etc-passwd-file/
 Sudo & the sudoers file
 https://www.redhat.com/sysadmin/sudo
Users & Groups in Windows
 Via GUI and cmd
 https://www.groovypost.com/howto/create-manage-user-accountprivileges-windows-10/
 With Powershell
 https://techcommunity.microsoft.com/t5/itops-talk-blog/how-tomanage-local-users-and-groups-using-powershell/ba-p/733544
Users & Groups in Mac
 Using GUI
 https://support.apple.com/guide/mac-help/add-a-user-or-groupmchl3e281fc9/mac
 Using commands
 https://simomor.medium.com/osx-users-and-groups-55e2fd4777df
SSH Key Points
Segway – History of Cyrptography
 https://www.exploratorium.edu/explore/secret-language
Intro to SSH
 SSH = Secure SHell
 Command interface / protocol for secure remote connections
 Tunnel between you and remote system
 Can use keys for authentication
 The AWS instance will ONLY allow use of key based authentication
 Password authenticated ssh is a thing
 Keys files provide more security
Key permissions
 Private keys must be private to you
 $ chmod 600 my_key_filename
 chmod = change file mode. Our primary use will be changing
permissions
 600 = 6 0 0
 6 = the username in charge of this file can read (4) and write (2)
 0 = no permissions for group members
 0 = no permssions for others who access the system
 Our private key should NOT be something anyone else but yourself
can have access to
The ssh command
 $ ssh -i my_key_file_name ubuntu@AWS_IP
 ssh is a command that will attempt to start a secure shell using the
details provided after ‘ssh’ is typed
 -i is a flag. It stand for identity file. After the -i flag, we put the path to
our private key
 my_key_filename is your private key. You can include a path (or folder
structure) to get to your key
 You might need to copy the key to a more convenient spot
 ubuntu is the default username we need to use to access the AWS
instance. Ubuntu is the only user that exists over there
 AWS_IP is the PUBLIC IP address to your AWS instance
SSH Resources
 https://www.cloudflare.com/learning/access-management/whatis-ssh/
 https://www.digitalocean.com/community/tutorials/understandingthe-ssh-encryption-and-connection-process
 Note: we will go more in depth later. These articles are detailed.
Don’t panic and carry a towel.
Git Setup
 Create GitHub account
 Go to Pilot -> this course -> Content -> Course Info -> Github
classrooms - join and create repo
 Select your wright.edu email
 If you misclick, let me know - I (or the Tas) can fix it
 Clone repo
GitHub - create & commit
 In your browser, go to your GitHub repository -
https://github.com/WSU-kduncan/ceg2350-YOURGITHUBUSERNAME
 Click the Add File button, then select "Create new file“
 When you are ready to save your work (or take a break), scroll to
the bottom to view the dialog regarding committing your work.
 Think of commits as save points.
 For each save point, you will write a message about what changed.
Intro to Git
 Version management software
 Savior of programmers / developers
 GitHub is a server / host of repositories
 Git is a program / command for version management
SSH Keys
 Keys come in pairs – public and private
 Public key - lock on remote system
 Private key - opens the lock on remote system
 Private keys are for you on your local system
 Protect the keys!
 Usually stored in a hidden folder called .ssh
 Once you create your AWS instance, you’ll need to create a key
pair for GitHub authentication
Setting up GitHub
 Create a key pair
 Do this for each system you want to hook to GitHub
 Find the public key of that pair
 look at your output from making your key
 Boom. Done.
 “git”, the program, knows how to find the private key (if you left the
defaults alone) and will check with GitHub to use the public key you
gave it
 This is because git is using the SSH protocol and agent - there are default
search flows set by the agent
Git config commands
 All commits must be signed / authored for future blaming
 $ git blame
 https://git-scm.com/docs/git-blame
 $ git config --global user.name "John Doe"
 $ git config --global user.email johndoe@example.com
Basic git commands
 git clone URL
 uses URL & sets up connection back to GitHub
 git add files/folders
 add files to be tracked (if they are new)
 git commit
 Commits are like checkpoints. You write a note of what changes
happened. Only the changes of files are captured in a commit
 git push
 pushes commits (think record of latest changes) to GitHub
 git pull
 Pulls remote (GitHub content) to local
More git examples
 git add vs git commit
 $ git commit -a
 For all files (that have already been added for tracking) commit all
changes
 $ git commit -m “message here”
 Write commit message on command line (instead of opening file editor
to create message)
So you cloned with HTTPS instead of
SSH
 If you cloned with SSH ignore this note.
 If you cloned with HTTPS, you need to authenticate each time you
push / pull (username + password)
 Change URL of remote repository:
 https://docs.github.com/en/get-started/getting-started-withgit/managing-remote-repositories#changing-a-remote-repositorys-url
 Or delete your local clone, then clone with ssh fresh
Git Resources
 Git cheat sheet
 https://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf
 Git essentials
 https://www.freecodecamp.org/news/the-essentials-of-git-explained-infive-minutes-d554019eded9/
Git – how the version tracking works
 Anatomy of a git commit
 https://blog.thoughtram.io/git/2014/11/18/the-anatomy-of-a-gitcommit.html
 Demo: `cat` a file, pipe to sha1?
 `echo -n "thoughtram" | openssl sha1`
 How git stores data
 https://how-to.dev/how-git-sto
```



