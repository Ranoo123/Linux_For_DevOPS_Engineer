# Linux_For_DevOPS_Engineer
date

Used to print the current date and time in the terminal.
echo "hello world"

Used to display lines of text or strings that are passed as arguments on the command line.
ls

Lists the contents of a directory.
pwd

Prints the present working directory.
whoami

Displays the username of the user currently logged in.
mkdir

Creates directories.
touch

Used to update the access and modification times of files, and to create new, empty files.
cd <directory_name>

Changes the current directory to the specified directory.
cd

Changes to the user's home directory.
cd /

Changes to the root directory (/), which contains all important system files in Linux.
df -h
Shows the amount of free disk space on each mounted disk.
man
Provides detailed information about a command or function, including its syntax, options, and examples.
cd ..
Moves up one directory level.
ping
Used to check the network connectivity between the host and another server or host.
touch file{2..10}.txt
Creates files named file2.txt through file10.txt.
rm -rf file*
The rm command is used to remove files or directories. The -rf option removes files recursively and forces the operation without prompting.
sudo
The sudo command stands for "Super User Do". It allows a permitted user to execute a command as the superuser or another user.
sudo apt-get update
Updates the package list on Ubuntu-based systems.
sudo apt-get install docker.io
Installs Docker on a Linux system (Ubuntu).
sudo apt purge docker
Uninstalls Docker from the system.
vi <filename>
Opens the vi command-line text editor to create or edit a file.
uptime
Shows how long the system has been running.
cd home
Changes to the /home directory.
mkdir -p /Rajan/file/myfile
Creates multiple directories along the specified path.
cd ~
Changes to the home directory of the user.
ls -a
Lists all files, including hidden files (those starting with a dot).
echo "hello-world" > hello.txt
Redirects the string "hello-world" into the file hello.txt.
vi
A command-line text editor used to create, edit, and modify files.
:wq!
Saves the file and exits the vi or vim editor.
Common vi/vim Commands:
i — Switch to insert mode.

Esc — Switch to command mode.

:w — Save the file and continue editing.

:wq or ZZ — Save and quit.

:q! — Quit without saving changes.

yy — Yank (copy) a line of text.

p — Paste the copied text.

o — Open a new line below the current line.

O — Open a new line above the current line.

A — Append text at the end of the line.

a — Append text after the cursor's position.

I — Insert text at the beginning of the line.

b — Move to the beginning of the current word.

e — Move to the end of the current word.

x — Delete a single character.

dd — Delete the entire current line.

Xdd — Delete a specified number of lines.

Xyy — Yank a specified number of lines.

G — Go to the last line of the file.

XG — Go to line X in the file.

gg — Go to the first line of the file.

:num — Display the current line's line number.

h — Move left by one character.

j — Move down by one line.

k — Move up by one line.

l — Move right by one character.

head hello.txt -n 2
Displays the first two lines of hello.txt.
cat <filename>
Displays the contents of the specified file.
head -n 4 example1.txt
Displays the first 4 lines of example1.txt.
tail
Displays the last ten lines of a file (default behavior).
tail hello.txt -n 3
Displays the last 3 lines of hello.txt.
sudo apt install nginx
Installs the NGINX web server.
Additional Steps:

To access the public IP of an EC2 instance, copy the public IP and paste it into another browser window.

Change to the NGINX directory: cd /var/www/html

Edit the default index file: sudo vi index.nginx-debian.html (Modify the file as required).

Again, copy the public IP of the EC2 instance and paste it in another browser. It will open the page of NGINX .

========================================================= User Management in Linux

sudo su

Use this command to log in as the superuser (root). The root user has all privileges.
sudo useradd -m Devra

Adds a user named Devra and the -m option creates the user's home directory.
sudo passwd Devra

This command sets a password for the user Devra.
su Devra

Switches to the user Devra.
cat /etc/passwd

Displays the contents of the /etc/passwd file, where you can see the list of users.
Create Multiple Users and Groups
Create users:


Copy

Copy
 sudo useradd -m user-1
 sudo useradd -m user-2
 sudo useradd -m user-3
Creates multiple users user-1, user-2, and user-3, each with their own home directory.
Create groups:


Copy

Copy
 sudo groupadd devops
 sudo groupadd Tester
Creates two groups: devops and Tester.
Add user to a group:


Copy

Copy
 sudo gpasswd -a user-1 devops
Adds user-1 to the devops group.
cat /etc/group

Displays the list of groups and users associated with each group.
File Permissions in Linux
File Permissions:

r - Read: Anyone can read this file.

w - Write: Anyone can modify this file.

x - Execute: Anyone can execute the file programmatically.

Example: -rw-rw-r--

First three (rw-): User has read and write permissions.

Second three (rw-): Group has read and write permissions.

Last three (r--): Others have read-only permission.

sudo chown Devra hello.txt
Changes the ownership of the file hello.txt to user Devra.
SSH (Secure Shell)
Launch an Ubuntu EC2 instance.
Go to the path /home/ubuntu/.ssh on your local machine.
Generate a .pem file and copy the private key's content.

SSH into another EC2 instance:

Go to the other instance and run the SSH command to connect using the copied private key.
Package Management in Linux
sudo apt-get update
Updates the package list for the system.
sudo apt upgrade
Upgrades installed packages to their latest available versions.
sudo apt install nginx
Installs the NGINX package.
sudo apt purge nginx
Uninstalls the NGINX package.
systemctl status nginx
Checks the current status of the NGINX service.
sudo systemctl stop nginx
Stops the NGINX service.
sudo systemctl start nginx
Starts the NGINX service.
GREP (Global Regular Expression Print)
grep junoon -r /home/ubuntu/
Searches for the string "junoon" recursively under the directory /home/ubuntu/.
grep junoon -ir /home/ubuntu/
Performs a case-insensitive search for "junoon" under /home/ubuntu/.
AWK
awk '/WAR/' Zookeeper_2k.log
Searches for the string "WAR" in the Zookeeper_2k.log file.
awk '/WAR/ {print $1}' Zookeeper_2k.log
Prints the first column for each line containing "WAR".
awk '/WAR/ {print NR $1$5}' Zookeeper_2k.log | grep ZooKeeperServer@793]
Prints specific fields from Zookeeper_2k.log and filters with grep for the key "ZooKeeperServer@793]".
awk '$2>="19:16:14" && $2<="19:18:14" && /WAR/ {print $1$2$5}' Zookeeper_2k.log
Filters and prints logs between specific timestamps containing the string "WAR".
SED (Stream Editor)
sed 's/Rajan@1234/****/g' password.txt
Replaces all occurrences of "Rajan@1234" with "****" in password.txt.
sed -i 's/Rajan@1234/RK/g' password.txt
Directly modifies password.txt, replacing "Rajan@1234" with "RK".
Find
find . -name *.log
Finds all .log files in the current directory and its subdirectories.
find /home/ubuntu -name *.log
Searches for .log files under the /home/ubuntu directory.
