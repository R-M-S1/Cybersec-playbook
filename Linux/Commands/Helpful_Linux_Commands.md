-ls is used to list files and directories in the current working directory, it can be given the options -lr which can be written as -rl and -r as well. 

Type is another command that allows you to see what type of command a command is, such as  internal commands, external commands, aliases, and functions to name a few. Type can also be used to remember what alias' are short for.

Which is another informative command that fetches where your system is pulling a certain command from. Say for instance the command -ls, by typing Which ls it will locate the file path that it is utilizing to get to the ls command. This is helpful for if a command is not behaving as you would expect it to.

Alias is a command that allows you to see which shorter commands you have mapped to shorter key lengths, say for instance you have a command that is 40 characters long and you have forgotten what you have shortened it to.

Functions can be utilized to complete a string of commands. 

Echo commands take something in quotes and regurgitates it back, using " " can ensure that the system does not misconstrue what you have written, however double quotes still allow for command substitution, variable substitution and some other misconfigurations. Single quotes ' ' prevent the shell from doing anything to the given text, which is useful for preventing it from substituting commands if given a $. You can also force the shell to use command substitution using backquotes ` `.

&& is used as an AND statement, if the first command succeeds, then the second will run, if the first command fails then the second will not continue. likewise, || can be used as a OR statement, if the first command succeeds then the second will not run, if the first command fails, the second will run.

Man is a command used for viewing the full page of another command, such as Man -ls. Man -k can be shortened to apropos. Man -f is the same as whatis. 


