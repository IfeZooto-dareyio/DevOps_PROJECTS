# FILE MANIPULATION

- SUDO COMMAND

`sudo apt upgrade`

The sudo command short for "superuser do" is used in linux to perform tasks that require administrative or root permissions. This is the result below for using the sudo command:

![Alt text](images/p1.png)

- PWD COMMAND

`pwd`

The pwd command is used to find the path of your current/present working directory. It has also has two acceptable options that can be used with it; -l which prints environment cariable content including symbol links, -P prints the actual path of the current directory.

![Alt text](images/P2.png)

- CD COMMAND

`cd /home/ubuntu/CommandsLinux` or `cd CommandsLinux`

The cd command is used to navigate through folders/directories.

![Alt text](images/p3.png)

- LS COMMAND

`ls`

The ls command is used to list files and directories within a system. Running the command without a flag will only show the current working directory's content.

![Alt text](images/p4.png)

Here are some flags that can be used with the ls command:

`ls -R` : This lists all the files in the subdirectories.

![Alt text](images/p5.png)

`ls -a` : This shows hidden files in addition to the visible ones.

![Alt text](images/p6.png)

`ls -lh` : This shows file sizes in easily readable formats like KB, MB or GB.

![Alt text](images/p7.png)

- CAT COMMAND

`cat filename`

The cat command is used to list, combine and write file contents to the standard output/terminal.

![Alt text](images/p8.png)

The `tac filename` can also be used but the contents are going to be displayed in reverse orders.

![Alt text](images/p9.png)

- CP COMMAND

`cp filename /destination_directory/`

The cp command is used to copy files or directories and their contents.

![Alt text](images/p10.png)

- MV COMMAND

`mv filename /destination_directory/`

The mv command on the other hand is either used for the purpose of moving a file or directory to another directory or used to rename a file.

![Alt text](images/p11.png)

To rename a file, the command syntax should look like this;

`mv original_name file_rename`

![Alt text](images/p12.png)

- MKDIR COMMAND

`mkdir [option/flag] directory_name`

The mkdir command is used to create one or multiple directories at once and set permissions for each of them.

![Alt text](images/p13.png)

To create another directory in your already created directory, we use this syntax;

`mkdir parent_directory/new_directory`

![Alt text](images/p14.png)

- RMDIR COMMAND

`rmdir -p /directory_name/`

The rmdir command, in the other hand is used to remove/permanently delete empty directory or directories.

![Alt text](images/p15.png)

- RM COMMAND

`rm filename`

We use the rm command to remove files within a directory, and its action is not reversible. So we must take caution while in the use of the command.

![Alt text](images/p16.png)

To remove multiple files at once, we use this syntax;

`rm filename1 filename2 filename3`

![Alt text](images/p17.png)

- TOUCH COMMAND

`touch filename`

The touch command is used to create new empty files.

![Alt text](images/p18.png)

- LOCATE COMMAND

`locate -i filename1*filename2`

The locate command is used to locate a file in the database system. The -i arguement is used to turn off case sensitivity incase you don't remember the file's exact name, while the * is used to look for contents which conyains two or more words.

![Alt text](images/p19.png)

- FIND COMMAND

`find [option] [path] [expression]`

The find command is used to search for files within a specific directory and performs subsequent operations.

![Alt text](images/p20.png)

- DF COMMAND

`df [options] [file]`

The df command is used to report the system's disk space usage, the information is shown in percentage and kilobyte (KB).

![Alt text](images/P21.png)

- DU COMMAND

`du directory_path`

![Alt text](images/p22.png)

- HEAD COMMAND

`head [option] [file]`

The head command is used to view the first ten lines of a text file. Adding an option lets you change the number of lines shown.

![Alt text](images/p23.png)

- TAIL COMMAND

`tail [option] [file]`

The tail command on the other hand is used to read the last ten lines of a text file. It allows users to check wether a file has new data or to read error messages.

![Alt text](images/p24.png)

- DIFF COMMAND

`diff [option] file1 file2`

The diff command short for difference, is used to compare two contents of a file line by line. After analyzing them, it will display the parts that do not match.

![Alt text](images/p25.png)

- TAR COMMAND

`tar [options] [archive_file] [file or directory to be archived]`

The tar command is used to archive multiple files into a tar file,which is a common linux format similar to the ZIP with optional compression

![Alt text](images/p26.png)

## FILE PERMISSIONS AND OWNERSHIPS

- CHMOD COMMAND

`chmod [option] [permission] [file_name]`

The chmod command is a command that modifies a file or directory's read, write and execute permissions.

![Alt text](images/p27.png)

- CHOWN COMMAND

`chown [option] owner[:group] file(s)`

The chown command changes the ownership of files in Linux systems. The user can change their own ownership but not others' unless they have root privileges.

![Alt text](images/p28.png)

- JOBS COMMAND

`jobs [option] jobID`

The job command is used to display all the running processes along with their statuses.

![Alt text](images/p29.png)

-KILL COMMAND

`kill [signal_option] PID`

The kill command is used to terminate an unresponsive program manually. It will signal misbehaving applications and instruct them to close their process.

![Alt text](images/p31.png)

 To kill a program using the above syntax, you must know its process identification number (PID). To know the PID of a program, we use the below command;

`ps ux`

![Alt text](images/p30.png)

- PING COMMAND

`ping [option] [hostname_or_IP_address]`

The ping command is a basic linux command used for checking whether a network or service is reachable, and it is also used to troubleshoot various connectivity issues.

![Alt text](images/p32.png)

- WGET COMMAND

`wget [option] [url]`

The wget command lets you download files from the internet, it runs in the background without hindering other running processes.

![Alt text](images/p33.png)

- UNAME COMMAND

`uname [option]`

The uname command or in full, unix name command will print detailed information and your linux system and hardware. The informations includes the machine name, operating system and kernel.

![Alt text](images/p34.png)

Some other useful options for more detailed informations are shown in the syntaxes below;

`uname -a`

This syntax prints all the system information.

![Alt text](images/p35.png)

`uname -s`

This syntax prints the kernel name.

![Alt text](images/p36.png)

`uname -n`

This syntax prints the system's hostname.

![Alt text](images/p37.png)

- TOP COMMAND

`top`

The top command in linux terminal will display all the running processes and a dynamic real-time view of the current system. It sums up the resource utilization, from the CPU to the memory usage.

![Alt text](images/p38.png)

- HISTORY COMMAND

`history [option]`

The history command is used in linux to list up to 500 previously executed commands, allowing you to reuse them without re-entering them. However only users with the sudo privileges can execute this command.

![Alt text](images/p39.png)

- MAN COMMAND

`man [command_name]`

The man command is used to display manual pages on your terminal screen, it can also be used as a search engine and help you find out what.

![Alt text](images/p40.png)

- ECHO COMMAND

`echo "string"` or `echo string > file`

The echo command is a built-in utility that displays a line of text or string using the standard output.

![Alt text](images/p41.png)

- ZIP, UNZIP COMMANDS

`zip [options] zipfile file1 file2….`

The zip command is used in linux to compress files into a ZIP file, a universal format commonly used in linux.

![Alt text](images/p42.png)

On the other hand, the unzip command extracts the zipped files from an archive. Here's the general syntax;

`unzip [option] file_name.zip`

![Alt text](images/p43.png)

- HOSTNAME COMMAND

`hostname [option]`

This command prints out your system’s hostname (or domain name). The default behavior for this command without any options will print just one word.

![Alt text](images/p44.png)

There are also other options to use for the command, but one of them is used to check for the ip address.

`hostname -i`

![Alt text](images/p45.png)

- USERADD, USERDEL COMMANDS

`useradd [option] username`

Useradd command is used to add new users to the system as linux is a multi-user system and only those with root/sudo privileges can run this command.

![Alt text](images/p46.png)

On the other hand, to delete a user account we use the userdel command;

`userdel [option] username`

![Alt text](images/p47.png)

- APT-GET COMMAND

`apt-get [options] (command)`

Apt-get is a command line tool for handling Advanced Package Tool (APT) libraries in linux. It is used to retrieve information and bundles from authenticated sources to manage, update, remove and install software and its dependencies.

![Alt text](images/p48.png)

- NANO, VI AND JED COMMANDS

`nano [filename]`

The nano command is a basic text editor.

![Alt text](images/p49.png)

The vi command is used to edit and create a text file. It also performs other operations like saving, opening, copying and pasting a file. To use the vi command, we use this syntax;

`vi [filename]`

![Alt text](images/p50.png)

And finally jed command which stands for "Just Edit". It's basically vi command but it is known for its simplicity and extensibility. To use the jed command, we use this command syntax;

`jed [filename]`

![Alt text](images/p51.png)

- ALIAS AND UNALIAS COMMAND

`alias Name=String`

The alias command will create an alias for any command that you want in your system.

![Alt text](images/p52.png)

The unalias command on the other hand is used to delete an existing alias. Its syntax is;

`unalias [alias_name]`

![Alt text](images/p53.png)

- SU COMMAND

`su [options] [username [argument]]`

The su command or switch user command is used to switch between existing users on the command line.

![Alt text](images/p54.png)

- HTOP COMMAND

`htop [options]`

The htop command is an interactive program that monitors system resources and server processes in real time.

![Alt text](images/p55.png)

- PS COMMAND

`ps`

The ps command or process status command produces a snapshot of all running processes in your system.

![Alt text](images/p56.png)