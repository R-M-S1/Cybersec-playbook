-ls is used to list files and directories in the current working directory, it can be given the options -lr which can be written as -rl and -r as well. 

Type is another command that allows you to see what type of command a command is, such as  internal commands, external commands, aliases, and functions to name a few. Type can also be used to remember what alias' are short for.

Which is another informative command that fetches where your system is pulling a certain command from. Say for instance the command -ls, by typing Which ls it will locate the file path that it is utilizing to get to the ls command. This is helpful for if a command is not behaving as you would expect it to.

Alias is a command that allows you to see which shorter commands you have mapped to shorter key lengths, say for instance you have a command that is 40 characters long and you have forgotten what you have shortened it to.

Functions can be utilized to complete a string of commands. 

Echo commands take something in quotes and regurgitates it back, using " " can ensure that the system does not misconstrue what you have written, however double quotes still allow for command substitution, variable substitution and some other misconfigurations. Single quotes ' ' prevent the shell from doing anything to the given text, which is useful for preventing it from substituting commands if given a $. You can also force the shell to use command substitution using backquotes ` `.

&& is used as an AND statement, if the first command succeeds, then the second will run, if the first command fails then the second will not continue. likewise, || can be used as a OR statement, if the first command succeeds then the second will not run, if the first command fails, the second will run.

Man is a command used for viewing the full page of another command, such as Man -ls. Man -k can be shortened to apropos. Man -f is the same as whatis. 



### Working With Text
stdin is terminal shorthand for standard input, its file discriptor number is zero
stdout is terminal shorthand for standard output, its file discriptor number is one
similarly, stderr is shorthand for standard error, its file discriptor number is two.

the redirection symbol, >, can be used in conjunction with the echo command to redirect the stdout to a spesific file. (the cat command can then be used to see the message in the file)
when you use the redirect symbole with stdout it first deletes the message currently in the file and replaces it with the new message, essentially save overwiriting, this is also called clobbering the file.

Using two redirect symbols, >>, it instead appends the new message with the old message rather than deleting the old message. 

It is further, possible to move the error text to a spesific file by using the previous command that produced the error and using 2> (2 being the file discriptor for stderr, and > being the redirect symbol to override previous text) along with a .txt doc.

you can seperate stdout and stderr outputs to their own distinct files by using the command "find /etc -name hosts > std.out 2> std.err" do note that, while not required, you may put a space inbetween the redirect symbol and the proceeding text, furthmore > with no number in front is assumed to be the same as 1>
It is also possible to make both stdout and stderr redirect to the same file by using "find /etc -name hosts > (file name) 2>&1"

stdin is typically given from the keyboard, however, it can also come from within files and commands, for example with the tr command, it translates text, for example making lowercase letters, uppercase without changing the case on the aforementioned letters. It is possible to use this in conjunction with a stdout file to make a all lowercase, or all uppercase, file by using tr a-z A-Z > upcase or vise versa.
you can then make the same file the opposite case by using tr A-Z a-z < upcase, switching the A and Z case based on your desired output. 

You can also use stdin to use one command as input for a different command, such as in the case of ls -l /etc | more, the ls -l /etc command is obsenely large and using it as input for the | more command allows the user to only see one page at a time. 
Similarly, with the cut command, it takes data and cuts it for use later, however this data can sometimes be long and run off the page. furthermore, it is unstructured. As such, you can ammend | sort to the end of the command to sort the data in alphabetical order, and further use | more after | sort, to view only one page of data at a time in alphabetical order.

sometimes the cat command is not useful for viewing excessively large files as they will run off the page and sometimes get cut off due to the terminal being able to house only so many lines of text in its memory, the more command can be used, as it is used in all linux distros, to view the same data but one page at a time, using the space button to "scroll" through the data. the Less command is similar to the more command, except it is not used in all distros, and it starts from the bottom of the text, utilizing a "search" feature similar to ctrl + f in a web browser, the n key is used to search forward in the text for the desired result while the N key is used to search backwards. Also unlike more, it does not automatically quit the command, you must press q to leave it. 

head is another command that can be used instead of cat, it shows the top ten lines of text in the given file, similarly the tail command shows the bottom ten lines. these commands can be ammended with -n where n is the lines of text you wish it to display. you can also pipe the output of a command such as ls /etc to a tail or head and ammend a number of lines you wish to view. You can also use the command head(or tail) -n -# where # is the number of lines from the top or bottom, which it would be the opposite of the command you pick, if heads than number of lines excluded from the bottom. 

grep command is used to search for spesific characters in a string of data. -E or egrep can also be used to find extended regular expressions, which is essentially a more powerful version of the grep command. -F or fgrep can be used to find literal chracters while ignoring their special meanings. 
the regular grep will match every single instance of what you are searching for, essentially the find command in a web browser but in a file. the ^ character can be used to search for a spesific word at the begining of the line. similarly, using the $ character can find the charcter at the end of the line, such as in 'root$' the '.' is used in conjunction with another character using grep to find the character with any character directly before the given character. if '.y' is used grep will find dy, fy, iy, instead of just y or words begining with y.
the | character can be used with grep as an OR seperater, such as beans | cheese | ham, beans, cheese, or ham. but it can only be used with egrep as grep sees it as a regular character. 
You can also search for a certain variation of a singular set of characters using the pipe, for example using egrep with 'no(b|n)' will have egrep search for nob or non, the parenthesis must be used elsewise egrep will search for nob or n
brackets can also be used with grep to look for a range of characters, such as in '[0-9]' will look for all integer numbers between 0 and 9.
the { bracket can be used in conjunction with the [ bracket to search for a sequence of numbers in the range [ provides, i.e. if [0-9] {3} then the system will look for 000 through 999 and any 3 number sequence inbetween.

### Understanding computer Hardware Lab 12
the command lscpu will inform you of the cpu type the linux distro is currently running on
the free command will tell you how much RAM and swap space is being used, you can also type free -m or -g for the amount in megabytes or gigabytes respectively. 
lspci will show you what devices are connected to the pci bus ammending -k to the commmand will also add the devices kernal driver and module used.
lsusb will list any connected usb devices including flash drives and mice.
lsmod will list the currently running modules of the device.

the fdisk command can let you manipulate disk storage information on the system, it can be used with or without the -l flag to be used non-interactively or interactively depending on what you desire to use fdisk for. in the first case you can see block devices such as hard drives, in interactive mode you can create partitions. 

### Where Data is stored Lab 13
/proc is a file directory that exists within the Memory of the device and communicates with the Linux Kernal directly. /proc contains a subdirectory for each running process on the system. /proc also houses information about the system itself in /proc/cpuinfo /proc/meminfo and /proc/devices. it also contains the subdirectory proc/sys. It is important to not directly edit these with a file editor but instead use echo or sysct1 to edit it and cat or sysct1 to view it. 

fg % followed by the job number will show you what the job is running to do. CTRL + Z will stop the job and return the CML to the users control. To have the process continue running in the background bg % job number should be used instead. 

kill % followed by the job number will immediantly cease the function of the job. alternatively killall job type can be used instead to kill all of a certain type of job.

using the top command you can see the acting jobs, by using the letter k you can kill a job with a certain PID, changing the following signal value from its default 15 to a 9 will make the kill forceful, bypassing a job preventing it from doing so.

pkill can be used instead of a PID if you wish to use the job name.

ps will list the processes currently running, ammending -e will display every process, regradless of where it is running. ammending -o will allow you to ammend options to tell the system what columns to output. you can further add --sort and one of the options to sort large to small for the spesific column.

The system logs are managed by two daemons that handle its messages, the syslogd daemon and the klogd daemon. klogd only handles kernal log messages and sends its information to syslogd.

messages generated at kernal boot time are stored in /var/log/dmesg and current kernal messages can be viewed with the command dmesg. /var/log holds the messages that syslogd creates. some processes also handle their own logging. 

### Lab 14: Network Configuration
By and large the most important resource for network config is the ifconfig command, as it will allow you to view your Internet Protocol Address. It presents information in two blocks, the first eth0, contains information revolving around your first Ethernet network card. The second, lo, pertains to loopback information, or the internal network interface. The second and third lines contain information regarding version 4 and 6 of the IP, being called IPv4 and IPv6 respectively. IPV4 is displayed as four decimal numbers ranging from 0 to 255 seperated by periods. IPv6 are 128-bit numbers in hexadecimal format ranging from 0 to f.

The Route command will show you the routing information in table form, this information will show you how your system will appear to devices you can route with. 

The dig command can be used to resolve a hostname to a spesific IP address. It can also be used to resolve other fully qualified domain names. The FQDN is the hostname (Hamburger) and the domain name (green.com). Furthermore, you can also use an IP address instead of a hostname or an DQDN to resolve with the dig command. 

netstat does a lot with network configuration, as such netstat --help is a useful command. Netstat can be used to find devices who are listening, or waiting, for a task to be given to them. 

|flag| use|
|--------|-------|
|-t| limits output to those listening to TCP ports|
|-l| limits the output to ports with listening services|
|-n| puts the network adresses in order numerically|

the ss command will also allow you to see connections from remote machines to the local machine, statistics about them, and etc. As such, it is a useful tool for troubleshooting issues with the local machine. 

### Lab 15 User and system security
*important note, a user has to be part of the sudo group for the sudo command to work also sudo asks for the current users password, not the root password*
|Command|Use|
|----|----|
|su/sudo| su can be used to switch users and begin a new shell as that user, and is typically used when you need to write a string of commands, Sudo is used when only a single command needs to be used, the root user must configure the sudo command before a regular user uses the command, the sudo effect remains for 15 minutes on Ubuntu if the root user account is not enabled|
|exit| exits the su root account|
|getent| gentent can be used to find account information that does not have to be specified in the local system|
|who| shows users on the current system|
|w| shows more detailed information about the users defined by the who command|
|last| last shows the login history stored in /var/log/wtmp file and displays all login and reboot records by default|

### Lab 16: Creating users and groups


|command|Use|flags|
|----|----|----|
|groupadd| intrestingly, creates a group name to put users into| -r puts the groups into reserve between 1-999|
|groupmod| modifies existing groups| -n can be used to change the name of the group, -g can be used to change the GID for the group|
|groupdel| deletes the group.|
|useradd| adds a user to a group| -D will provide details useful for adding a user while -k will allow you to use a different SKEL directory instead of the default one. -f can be used with a numerical value after the flag to change the value that lets users still login to their account for x number of days after their password expires. -G should be used with a group name to ensure the proper group is given the new user.|
|usermod| modifies the user| -L will lock the user account, -U will unlock it.|
|userdel| will delete the user| -r will also delete the home derectory as well as the mail with the user account.|
|lastb| shows all failed login attempts|


### Lab 17: Ownership and permissions

|character when ls -l is used| what it means|
|-------|--------|
|d| indicates a directory|
|-| indicates a regular file|
|l| is a symbolic link|
|b| is a block device file|
|c| is a character device file|
|p| is a pipe file|
|s| is a socket file|

the nine characters that follow the begining character are broken into three blocks, block one indicates the user owners permissions, the next block indicates the group owner permissions, and the next block indicates every one elses, the characters for permissions are r (read), w (write), and x (execute), a - indicates that the block does not have that permission (eg. r-- or rw-) 

|commands| their purpose|flag|
|---|---|----|
|ls -la| lists the hidden files in the current directory and who they belong to.|
|chmod| chmod can be used to edit a files permissions, this is done by indicating what person you want to remove, rg. o for others, and the permission(s) you want to remove. a can be used to edit all users, u for user and g for group. + can be used to add permissions while - will take them away. chmod can also be used in octal notation, using 4 for read, 2 for write, and 1 for execute. these can be added to make 7 when giving/removing commands.|
|stat| can view statistics for files, including the octal notation for them, under ACCESS|
|chown| can only be used by the root user, changes a directory for both the user and group of the file.|
|chgrp| can be used by both the root user and the owner of the file. as such, it only changes the group of the file. If a non-root user attempts to use this command they cannot change group ownership unless they are a member of the group.| -R can be used to change ownership of the group recursively (changing the files, but not the base directory)|

*** Lab 18: Special files and directories

the letter t can be in the executable permission block, this indicates a sticky bit permission, wherin only the user that created a file can delete the file. 

the letter s in the user execute permission colume indicates that the file has a setuid, it will run as the user executing the file instead of thw owner of the file. if the letter s is instead in the group block it is a setgid which will run as the group that owns it instead of the group the user belongs to

** Hard Links vs soft links

hard links use the existing inode to create another directory. It adds a name to be associated with the existing file.
soft links are like hard links in that they are associated with a target file, except they use their own inode code and do not add to the list of linked files. 

|Command| use| flag|
|----|----|---|
|ln| when used with an existing file and another name, it will link the target to the new name.| -s creates a soft link instead of a hard link|
