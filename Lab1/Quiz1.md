
>vim alpha - opens a text editor for the file names alpha in the current directory

>pwd -displays the path (or location) to the current directory

>man shows a manual for the command / program ls

>cp beta alpha creates a copy of beta name alpha in the current directory

> cat aplha prints the contents of the file named alpha in the current directory to standard output (the terminal)

>cd new changes directory to directory named new

>touch beta creates a file named beta in the current directory

>mv beta alpha moves (or renames) beta to alpha

>ls shows contents of folder

>mkdir new creates a directory named new within the current directory

	
> git pull - synchronizes commits (change) on the remote repository (in the case of this course, the remote repository is hosted on GitHub) with the local clone

>git add - adds file1 for tracking or adds changes in file1 to be committed

>git commit -creates a "checkpoint" of changes made.  When made, a message also must be provided that should be a description of what changes are included.

>git push- synchronizes local commits to the remote repository (in the case of this course, the remote repository is hosted on GitHub).

>git status- shows information about what is happening in a folder that is a git repository.  This can include noting what files have not been tracked, what changed files are part of the next commit, and how many commits are ready to be pushed.

```
Question 2		
After running the following command:
cat /etc/shadow

The output is: 
cat: /etc/shadow: Permission denied

Assuming the user running the command is a member of the sudo group, how can I view the file's contents?

Question options:
Selected
sudo cat /etc/shadow
```


Question 3		
Match the commands to their description

```
chmod 542 file1
changes file1 to have the following permissions:

user / owner of file1 can read and execute

group owning file1 can read

others can edit file1
```
```
adduser alpha	
if the user alpha does not exist, will provide a series of prompts to get information for the new user, including password and phonebook information
```
```	
chgrp beta file1	
changes the group ownership of the file file1 to beta
```

```
chown alpha file1
changes the owner of the file file1 to alpha
```

```
usermod -G alpha beta	
modifies a user's account to add alpha to the beta group (if it exists)
```
whoami	
prints username associated with the current effective user id

```
su alpha
switches user to alpha, may prompt for user's password when switching
```

```
addgroup beta
adds a group named beta to the system
```

