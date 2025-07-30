
 # LINUX:
  why learn linux:
  -Open source
  - many different distributions( red hat enterprises- we need to pay )
  - fast growing
  - inexpensive
  - stable ( compared to windows )
  - scales well up and down.
  - also can be used as a workstation and worktop
  - often used in deploy applictions(database)
  - more employable


### what is linux?
    -spinoff of Unix
    -made up of kernel(core,os),plus many libraries + utilities / tools that rely on it.

### what is bash?
    -type of shell
    - shell is software/interface that runs commands(AKA a command line interpreter)
    - stands for Bourne Again Shell.
    - range of shell, the most common default is Bash
    - root (/) /bin/bash -- delimiter

### what is ssh
    SSH stands for Secure Shell. 
    It is a network protocol used to securely access and manage remote systems (like servers) over a network.

   
### whenever we have stopped EC2 instance we have to logging back using ssh public key because everytime when we stop the EC2 the public key changed. so we need to sing up saying yes.

 
### Steps to create a EC2 instance
- Open the aws account using credential .
- click EC2 instance and give a name.
- Change the name of the file.
- create EC2
- it will automatically generate a key on the next page
- open gitbash
- go to .ssh folder
- enter the ssh keys which is in EC2 screen.

#### list the contents of a directory with detailed information .
ls -al
#### Display the present working directory
pwd
#### Create a directory
mkdir directory
#### It allows users to view the reference manuals of a command or utility used in the terminal.
man
#### Remove (delete) file
rm file
#### Remove the directory and its contents recursively
rm -r directory
#### Force removal of file without prompting for confirmation
rm -f file
#### Forcefully remove directory recursively
rm -rf directory
#### Copy file1 to file2
cp file1 file2
#### Rename or move file1 to file2. If file2 is an existing directory, move file1 into directory file2
mv file1 file2
#### Create symbolic link to linkname
ln -s /path/to/file linkname
#### Create an empty file or update the access and modification times of file.
touch file
#### View the contents of file
cat file
#### Browse through a text file
less file
#### Display the first 10 lines of file
head file
#### Display the last 10 lines of file
tail file
#### Display the last 10 lines of file and "follow" the file as it grows.
tail -f file
#### To go up one level of the directory tree.  (Change into the parent directory.)
cd ..
#### Go to the $HOME directory
cd
#### Change to the /etc directory
cd /etc
#### show the history
history
#### show all the shell
cat/etc/shells
####  clear the history
history -c
#### command for help
man , --help
#### command to quit
first - q
second- ctrl+z
third(force quit) - ctrl+c
#### processor which are running
ps -p $$

### Root User
The root user is the superuser in Linux systems. 
Think of it as the administrator of the entire system.

#Root User:	The most powerful user on the system (admin privileges)

The first command to run : sudo apt update --(Sudo super user do command)

### Root Directory
The root directory is the top-level directory in the Linux file system. 
It is represented by a forward slash (/).
  -All other directories (like /home, /etc, /bin) are inside this root.
  -It’s like the “C:\” drive on Windows — the starting point of the entire file structure.
#Root Directory (/)	The top-most folder in the file system hierarchy

### sudo upgrade -y 
sudo apt upgrade -y is dangerous because it upgrades all packages without asking for confirmation. 
This can accidentally install unstable updates, break existing applications, or cause system issues. 
You won’t get a chance to review or stop risky changes. In production we  never run upgrade, it has to 
be done in testing.


### nano:
  - #!/bin/bash
  - update
  - upgrade
  - install nginx
  - config nginx (change the seeting one or more lines and save the file , once you saved, you should  restart to see the changes in setting )
  - restart nginx which restarts the process
  - enable nginx which means it will be added to the start up menu. ( it will start  the vm  automatically when vm restart)

#### ENVIRONMENTAL VARIABLE:
 environment variables are essential components that enable 
 users to store and access information across various processes and user sessions.
 #### #!/bin/bash - 
 
### syntax
echo $user
### printenv - print all the environement variable
printenv "name" give the enviroment variable incapital letter. 
### syntax:
export MYNAME =ramya (export command will change this into enviromental variable)

### source .bashrc (it update the bashrc)

## processes:
what is processes?
   - sort of two program run in the memory.
   - software/programme loaded into memory
   - Single-core CPU means the processor had only one core 
   - It could only execute instructions from one process at a time.
   - multiple core can process instructions for multiple processes at the same time
#### TWO TYPES OF PROCESSES:
 - user processes
 - system processes
 - 
### ps aux - Used for seeing all processes on the system with detailed info.
 ### top
-top is a real-time system monitoring tool.
- It shows a live, updated list of running processes. 
- Provides information about CPU and memory usage. 
- Helps you understand system load and resource consumption.
### Htop:
  - A more user-friendly and colorful alternative to top. 
  - Displays the same real-time info but with a better interface.



 - Shift + P	Sort processes by CPU usage (highest first)
 - Shift + M	Sort processes by Memory usage (highest first)
 - Shift + N	Sort processes by PID (process ID)


#### Kill command:
    -In Linux, the kill command is used to terminate processes by sending signals to them. 
    - Kill -15 standard kill command in graceful way
    - kill -9 Brute force kill 
    - Kill -15 terminate the child process and then terminate the parent process but sometime later the parent process will start generating child process.
    - Kill -9 completely kill the parent process but child process still in memory without any parent process controlling. 
  

#### Why is managing file ownership important?
  Managing file ownership is important because it controls who can access, modify, or delete files. This helps keep the system secure and ensures that only the right users can manage certain files.

####  What is the command to view file ownership?
 : ls -n

####  What permissions are set when a user creates a file or directory? Who does the file or directory belong to?
 By default, the file/directory belongs to the user who created it and their primary group.

 File: rw- (read, write) for owner; others may get fewer rights.

 Directory: rwx (read, write, execute) for owner;

#### Why does the owner, by default, not receive X (execute) permissions when they create a file?

Because most files are not meant to be run (like text files or documents).
- Most files people create (like text files, documents, or scripts) are meant to be read or written, not run as programs.
- If every new file had execute permission, it would be easier for malicious scripts or programs to run accidentally or without the user's knowledge.

####  What command is used to change the owner of a file or directory?

 chown command ( chown newowner filename-syntax)

#### Does being the owner of a file mean you have full permissions on that file? Explain.
    No, being the owner of a file does not automatically mean you have full permissions.

    - Permissions (read, write, execute) are set separately for the owner, group, and others.
    - The owner can have limited permissions (e.g., read-only) unless explicitly granted more.

    - The owner can usually change the file's permissions (using chmod), which gives them indirect control.
  
#### If you give permissions to the User entity, what does this mean?
      This refers to permissions granted to the owner of the file.
   - if user permissions are rw-, the file owner can read and write, but not execute the file.
  
#### if you give permissions to the Group entity, what does this mean?
      This applies to users who are members of the group associated with the file.

#### If you give permissions to the Other entity, what does this mean?
      This applies to all users who are neither the owner nor in the file's group.

#### Scenario: User (owner) has read-only, Group has read/write, Others have read/write/execute. You are logged in as the owner. What permissions do you have?
    read only permission . 

#### Analyzing this line from ls -l:

    -rwxr-xr-- 1 tcboony staff  123 Nov 25 18:36 keeprunning.sh
-  its a file (not a directory as d is not there )
-  rwx - owner has read write and execute permission.
-  r-x group has read and execute permission
-  r others has only read permission. 
-  tcboony - owner name
-  staff - groupname
-  123 file bytes size
-  Nov 25th 18.36 -last modified date and time
-  keeprunning.sh - File name
  

#### What numeric values are assigned to each permission?   
  - Read -4
  - write - 2
  - execute - 1

#### What numeric values would you use to assign read + write permissions?
     for read + write = 4+2 = 6

#### What numeric values would you use to assign read, write and execute permissions?
     for read +write+execute = 4+2+1=7

#### What numeric values would you use to assign read and execute permissions?
     for read +execute = 4+1 =5

#### Often, a file or directory's mode/permissions are represented by 3 numbers. What do you think 644 would mean?
     644 -> rw-r-r -> owner(read and write),group(read only),others(read only)

#### What command changes file permissions?
    chmod (stands for change mode)

#### change permissions on a file, what must the end user be? (2 answers)
    The file owner
    The superuser (root)
#### Give examples of some different ways/syntaxes to set permissions on a new file (named testfile.txt) to:
    testfile.txt
    user - r
    group - read +write+execute
    other - read + write
    -chmod u=r,g=rwx,o=rw testfile.txt

    -chmod a+x testfile.txt(it add execute permission to all users,group,others)

    -chmod g-w testfile.txt(remove write permission away from group)

    -numeric values 
     user = read + write =6
     group = read =4
     other = no access =0

     chmod 640 testfile.txt