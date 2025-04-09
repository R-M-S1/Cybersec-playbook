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
