### LAB 11
vi is one of the most common text editiors and is featured on every Linux distro, however, other examples exists such as nano and gedit, vi exists in all of them. 

vi has two modes, insert and command, insert, as obvious as it may be, inserts the text doc, while command lets you save, navigate, search, and exit the text doc. 

As with most editing commands, using "vi file name" where file name is, the file name, it creates a new file for you to edit.
In command mode you can utilize certain keys to adjust your cursor

| Key | Description|
|------|---------------------------------------------|
| J | Moves cursor down one line (same as down arrow)|
| K | Moves cursor up line (same as up arrow)|
| L | Moves cursor to the right one character (same as right arrow)|
| H | Moves cursor to the left one character (same as left arrow)|
| W | Moves cursor to beginning of next word|
| E | Moves cursor to end of word|
| B | Moves cursor to beginning of previous word|
| $ | Moves cursor to end of current line (same as End key)|
| 0 | Moves cursor beginning of current line (same as Home key)|
| 3G | Jumps to third line (nG jumps to the nth line)|
| 1G | Jumps to the first line|
|Shift+G | Jumps to the last line|
| l | moves forward one space|
| ~ | shifts letter case|
| a | change from command to insert mode| 
| Esc| change from insert mode to command mode| 
| o | add a new blank line under the current line| 
| O | add a new blank line above the current line| 

As you press esc when in command mode or when first creating the document you will likely want to save your text, the following are the keys and their descriptions of how to do so.

|Key| Description|
|-------|-------------|
|:x| Save and close the file|
|:wq| Write to file and quit|
|:wq!| Will write to a read-only file, if possible, and quit.|
|ZZ| Will save and close. Notice that no colon : is used in this case.|
|:q!| Will quit without saving changes.|
|:e!| Discard changes and reload file.|
|:w!| write to read only if possible.| 

Dw can be used to delete the word the cursor is currently on while u can undo the last operation. you can use a number before dw to modify how many words will be deleted. using the x character can be used to delete letters one by one. u can also be modified with a number to adjust how many prior actions you would like undone. Furthermore, instead of typing xxxxxxxxx can be instead replaced with 9x to delete 9 characters. using a capital x in 9X will instead delete the characters to the left of the cursor. Using dd will delete the line the cursor is currently on and can also be adjusted with a number. whatever was deleted last can be pasted using the letter p. d$ will delete every character from the cursor to the end of the line on the right. J will combine the current and next line and can also be modified with a number. yw will 'yank' or copy the current word the cursor is on. 

Pressing any other keys could result in being back in the insert mode, using :q! and hitting enter will exit without making changes. 

