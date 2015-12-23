## Keyboard speed 2m

  Faster erasing ( 9.2 )
  Filename completion ( 9.8 , 9.9 , 9.10 )
  102 Command Line Editing
  clear
  exit
  
tab completion
clear/exit/cancel
cursor line movement
cursor charachter movement

## Keyboard speed 4mw

  Command 	Function
  CTRL-b 	Move backward one character (without deleting).
  CTRL-f 	Move forward one character.
  CTRL-d 	Delete one character forward.
  CTRL-z 	Move to beginning of line.
  CTRL-e 	Move to end of line.
  CTRL-k 	Delete ("kill") forward to end of line.
  CTRL-w 	Delete ("wipe") backward to beginning of line.
  CTRL-y 	Retrieve ("yank") last deleted item.
  CTRL-c 	Delete entire line.

  Command Line Editing
  bash uses a library (a shared collection of routines that different programs can use) called Readline to implement command line editing.

  We have already seen some of this.

  We know, for example, that the arrow keys move cursor, but there are many more features.

  Think of these as additional tools that we can employ in our work.

  It’s not important to learn all of them, but many of them are very useful.

  Pick and choose as desired.
  Note: Some of the key sequences below (particularly those that use the ALT key) may be inter- cepted by the GUI for other functions.

  All of the key sequences should work properly when using a virtual console.
  Cursor Movement
  Table 8-1 lists the keys used to move cursor.
  Table 8-1: Cursor Movement Commands
  Key Action
  CTRL-A Move cursor to the beginning of the line.
  CTRL-E Move cursor to the end of the line.
  CTRL-F Move cursor forward one character; same as the right arrow key.
  CTRL-B Move cursor backward one character; same as the left arrow key.
  ALT-F Move cursor forward one word.
  ALT-B Move cursor backward one word.
  CTRL-L Clear the screen and move cursor to the top left corner.

  The clear command does the same thing.
  Modifying Text
  Table 8-2 lists keyboard commands that are used to edit characters on the command line.
  Cutting and Pasting (Killing and Yanking) Text
  The Readline documentation uses the terms killing and yanking to refer to what we would commonly call cutting and pasting.

  Table 8-3 lists the com- mands for cutting and pasting.

  Items that are cut are stored in a buffer called the kill-ring.

  Table 8-2: Text Editing Commands
  Key Action
  CTRL-D Delete the character at cursor location.
  CTRL-T Transpose (exchange) the character at cursor location with the one preceding it.
  ALT-T Transpose the word at cursor location with the one pre ceding it.
  ALT-L Convert the characters from cursor location to the end of the word to lowercase.
  ALT-U Convert the characters from cursor location to the end of the word to uppercase.
  Table 8-3: Cut and Paste Commands
  Key Action
  CTRL-K Kill text from cursor location to the end of line.
  CTRL-U Kill text from cursor location to the beginning of the line.

  ALT-D Kill text from cursor location to the end of the current word.
  ALT-BACKSPACE Kill text from cursor location to the beginning of the cur rent word.

  If cursor is at the beginning of a word, kill the
  previous word.
  CTRL-Y Yank text from the kill-ring and insert it at cursor location.
                            THE META KEY
  If you venture into the Readline documentation, which can be found in the "READLINE" section of the bash man page, you will encounter the term meta key.

  On modern keyboards this maps to the ALT key, but it wasn’t always so.
  Back in the dim times (before PCs but after Unix) not everybody had their own computer.

  What they might have had was a device called a terminal.

  A ter- minal was a communication device that featured a text-display screen and a keyboard and had just enough electronics inside to display text characters and move cursor around.

  It was attached (usually by serial cable) to a larger computer or the communication network of a larger computer.

  There were many different brands of terminals, and they all had different keyboards and display feature sets.

  Since they all tended to at least understand ASCII, software
       Advanced Keyboard Tricks 71
      developers wanting portable applications wrote to the lowest common denom- inator.

  Unix systems have a very elaborate way of dealing with terminals and their different display features.

  Since the developers of Readline could not be sure of the presence of a dedicated extra control key, they invented one and called it meta.

  While the ALT key serves as the meta key on modern keyboards, you can also press and release the ESC key to get the same effect as holding down the ALT key if you’re still using a terminal (which you can still do in Linux!).
   Completion
  Another way that the shell can help you is through a mechanism called com- pletion.

  Completion occurs when you press the TAB key while typing a com- mand.

  Let’s see how this works.

  Say your home directory looks like this:
  [me@linuxbox ~]$ ls
  Desktop ls-output.txt Pictures Templates Videos Documents Music Public
  Try typing the following but don’t press the ENTER key: [me@linuxbox ~]$ ls l
  Now press the TAB key:
  [me@linuxbox ~]$ ls ls-output.txt
  See how the shell completed the line for you? Let’s try another one.
  Again, don’t press ENTER:
  [me@linuxbox ~]$ ls D Press TAB:
  [me@linuxbox ~]$ ls D
  No completion—just a beep.

  This happened because D matches more than one entry in the directory.

  For completion to be successful, the "clue" you give it has to be unambiguous.

  We can go further:
  [me@linuxbox ~]$ ls Do Then press TAB:
  [me@linuxbox ~]$ ls Documents
  The completion is successful.
  While this example shows completion of pathnames, which is comple- tion’s most common use, completion will also work on variables (if the beginning of the word is a $), usernames (if the word begins with ~), com- mands (if the word is the first word on the line), and hostnames (if the beginning of the word is @).

  Hostname completion works only for host- names listed in /etc/hosts.
  A number of control and meta key sequences are associated with com- pletion (see Table 8-4).
  Table 8-4: Completion Commands
  Key Action
  ALT-? Display list of possible completions.

  On most systems you can also do this by pressing the TAB key a second time, which is
  much easier.
  ALT-* Insert all possible completions.

  This is useful when you want to use more than one possible match.
  There quite a few more that I find rather obscure.

  You can see a list in the bash man page under the "READLINE" section.

  line-kill character - typically CTRL-u o

  "word-erase" character, usually CTRL-w, which deletes only back to the previous whitespace

  TAB filename completion

  CTL + L clear
  CTL + D exit
  CTL + C cancel/quit

### VO 300w

  (Assumed knowledge)

  *tab

  Completion occurs when you press the TAB key while typing a command.

  $ ma TAB

  $ whatis a2p

  $ ls TAB
  $ ls D TAB

  *clear/exit

  CTL + L clear
  CTL + D exit
  CTL + C cancel/quit

  *cursor line

  (option as meta)

  CTRL-A Move cursor to the beginning of the line.
  CTRL-E Move cursor to the end ofline.

  *cursor word

  ALT-F move forward to next word
  ALT-B move backward to previous word

  ALT-BACKSPACE Kill text from cursor beginning ofcurrent word.

  ALT-D Kill text from cursor end of current word.

  ALT-L cursor end ofword to lowercase.

  ALT-T Transpose the word at cursor location with the one pre ceding it.

  ALT-U Convert the characters from cursor end ofword to uppercase.

  CTRL-K Kill text from cursor end of line.

  CTRL-T Transpose (exchange) the character at cursor location with the one preceding it.

  CTRL-U Kill text from cursor beginning ofline.

  CTRL-d 	Delete one character forward.

  CTRL-k 	Delete ("kill") forward to end of line.

  CTRL-w 	Delete ("wipe") backward to beginning of line.

  CTRL-y 	Retrieve ("yank") last deleted item.

  ctrlw is the standard "kill word" (aka werase).

  ctrlu kills the whole line (kill).


