# CEG2350 - Lab Work
Lab work for CEG 2350 at Wright State University, Department of Computer Science and Engineering

## Lab 02

- Name:Research Sharma Bhattarai
- Email: sharmabhattarai.2@wright.edu

Instructions for this lab: https://pattonsgirl.github.io/CEG2350/Labs/Lab02/Instructions.html

## Part 1 Answers

Full / absolute path to your private key file: Downloads/labsuser.pem or /home/ubuntu

Command to SSH to AWS instance:

sudo ssh -i ~/Downloads/labsuser.pem ubuntu@44.215.47.201

[Place your ssh command here]

sudo ssh -i ~/Downloads/labsuser.pem ubuntu@44.215.47.201

## Part 2 Answers

1. `chmod u+r bubbles.txt`
   
    - Means: It adds the read permission for the owner of bubbles.txt
    - Assessment: it is only valid or correct if the aim is to allow the owner to read the file.
2. `chmod u=rw,g-w,o-x banana.cabana`
    - Means: It gives the owner read and write access, removes writes from the group. and remove execute from other
    - Assessment: It works as intended to restrict others while giving owner full control.
3. `chmod a=w snow.md`
    - Means: Here the owner gets full access, and the group can write read and others only can execute 
    - Assessment: No user can read or run the file, they only can ovverwrite it.
4. `chmod 751 program`
    - Means:Here the owner gets full access, and the group can write read and others only can execute
   - Assessment:it is a god choice for an executable program where owner can edit, group can read, others can only run
5. `chmod -R ug+w share`
    - Means: It recursively gives write permission to owner and group on everything inside
    - Assessment: It is correct if we want both user and the group to edit everything inside.

## Part 3 Answers

1. Command to create new user: sudo adduser thanos
2. Path to new user's home directory: /home/thanos
3. Evaluate if `ubuntu` can add files to new user's home directory: No unlesss we change the permission.
4. Command to switch to new user: sudo su - thanos
5. Command(s) to go to new user's home directory:cd /home/thanos
6. Evaluate if new user can add files to user's home directory: I No
7. Command to return to `ubuntu` user: sudo su - ubuntu
8. Command to return to `ubuntu` home directory: cd ~

## Part 4 Answers

1. Command(s) to create group named `squad` and add members: sudo groupadd squad
2. Command(s) to add `ubuntu` & user to group `squad`: aG squad ubuntu, thanos
3. Command(s) to allow `squad` to view the `ubuntu` user's home directory contents: sudo chmod g+rx /home/ubuntu
4. Command(s) to modify `share` to have group ownership of `squad`: sudo chgrp -R squad share
5. Describe your tests and commands with the user account: Logged in  as thanos and ran in ls /home/ubuntu
6. Describe the full set of permissions / settings that enable the user to make edits: Group = squad \
   Directory permission = rwx for user plus group
   thanos is member of squad

## Part 5 Answers

For each, write the command used or answer the question posed.

1. Command(s) to make file using `sudo`: sudo touch research.txt
2. Command(s) to make file with `root`: sudo -i touch researchrootfile.txt exit
3. Describe / compare ownership and permissions of files: Files created with sudo or as root are owned by roots
4. Which account can do what actions? (Type Y or N in columns)

Contents inside of `share`
| Account   | Can View  | Can Edit  | Can Change Permissions    |
| ---       | ---       | ---       | ---                       |
| `root`    |         Y  | Y          | Y                          |
| `ubuntu`  |          Y |  Y         |  N                         |
| `BOB`     |           Y|   Y        |   N                        |

`madewithsudo.txt`
| Account   | Can View  | Can Edit  | Can Change Permissions    |
| ---       | ---       | ---       | ---                       |
| `root`    |      Y     | Y          | Y                          |
| `ubuntu`  |     Y      |  N         |  N                         |
| `BOB`     |      Y     |   N        |   N                        |

5. Command(s) to modify permissions: sudo chmod 664 test.txt
6. How to give user account `sudo`: sudo usermod -aG sudo thanos

## Citations

To add citations, provide the site and a summary of what it assisted you with.  If generative AI was used, include which generative AI system was used and what 

TA
Classmates 
Googleprompt(s) you fed it.
