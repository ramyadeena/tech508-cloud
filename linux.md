
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

 
## Steps to create a EC2 instance
- Open the aws account using credential .
- click EC2 instance and give a name.
- Change the name of the file.
- create EC2
- it will automatically generate a key on the next page
- open gitbash
- go to .ssh folder
- enter the ssh keys which is in EC2 screen.

### list the contents of a directory with detailed information.
ls -al
### Display the present working directory
pwd
### Create a directory
mkdir directory
### It allows users to view the reference manuals of a command or utility used in the terminal.
man
### Remove (delete) file
rm file
### Remove the directory and its contents recursively
rm -r directory
### Force removal of file without prompting for confirmation
rm -f file
### Forcefully remove directory recursively
rm -rf directory
### Copy file1 to file2
cp file1 file2
### Rename or move file1 to file2. If file2 is an existing directory, move file1 into directory file2
mv file1 file2
### Create symbolic link to linkname
ln -s /path/to/file linkname
### Create an empty file or update the access and modification times of file.
touch file
### View the contents of file
cat file
### Browse through a text file
less file
### Display the first 10 lines of file
head file
### Display the last 10 lines of file
tail file
### Display the last 10 lines of file and "follow" the file as it grows.
tail -f file
### To go up one level of the directory tree.  (Change into the parent directory.)
cd ..
### Go to the $HOME directory
cd
### Change to the /etc directory
cd /etc
### show the history
history
### show all the shell
cat/etc/shells
###  clear the history
history -c
### show the second item in the history
!2
### processor which are running
ps -p $$
