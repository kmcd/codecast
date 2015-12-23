## History 2m

  Chapter 11: The Lessons of History
  16.12 Setting Shell History Options
  106 Using History
  
# History 01
## What is it?
  View & re-use every comand you type in

## Why is it useful?
  Don't have to remember what or how you did something; e.g. what was that command to ...

## You will be able to ...
  view commands
  search commands
  repeat command execution

## Examples
  history file
  scroll up though commands
  repeat last command
  repeat command by number
  search command with CTRL+R
  search command with grep filter

## Points to note
  history behavoiur is controlled from .bash_profile

## Recap
## Next steps

## History 2m

  The history command lists the saved commands, each with an identifying number.

  history 20 shows your last 20 commands

  I use !$ so much that it's almost a single character to me. It means "take the last thing on the previous command line."

  The $HISTFILESIZE variable sets the number of lines permitted in the $HISTFILE. The default for $HISTSIZE is 500 lines, and $HISTFILE is ~/.bash_history unless you are in POSIX mode, in which case it’s ~/.sh_history.

  Increasing $HISTSIZE may be useful, and unsetting it causes the $HISTFILE length to be unlimited.

  Changing $HISTFILE probably isn’t necessary, except that if it is not set or the file is not writable, no his- tory will be written to disk.

  The $HISTSIZE variable sets the number of lines permit- ted in the history stack in memory.

  $HISTIGNORE and $HISTCONTROL control what goes into your history in the first place.

  $HISTIGNORE is more flexible since it allows you to specify patterns to decide what command lines to save to the history.

  $HISTCONTROL is more limited in that it sup- ports only the few keywords listed here (any other value is ignored):

  ignorespace
  Command lines that begin with a space character are not saved in the history list.

  ignoredups
  Command lines that match the previous history entry are not saved in the his- tory list.

  ignoreboth
  Shorthand for both ignorespace and ignoredups.

  erasedups
  All previous command lines that match the current line are removed from the history list before that line is saved.

  If $HISTCONTROL is not set, or does not contain any of these keywords, all commands are saved to the history list, subject to processing $HISTIGNORE. The second and sub- sequent lines of a multiline compound command are not tested, and are added to the history regardless of the value of $HISTCONTROL.

  (Material in the preceding paragraphs has been adapted from Edition 2.5b of The GNU Bash Reference Manual for bash Version 2.05b, last updated July 15, 2002; http://www.gnu.org/software/bash/manual/bashref.html.)

  As of bash version 3, there is a fascinating new variable called $HISTTIMEFORMAT. If set and non-null, it specifies an strftime format string to use when displaying or writing the history. If you don’t have bash version 3, but you do use a terminal with a scroll- back buffer, adding a date and time stamp to your prompt can also be very helpful. See Recipe 16.2, "Customizing Your Prompt." Watch out because stock bash does not put a trailing space after the format, but some systems (e.g., Debian) have patched it to do so:

  bash-3.00# export HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S'
  bash-3.00# history
     1  2006-10-25_20:48:04ls -la
     2  2006-10-25_20:48:11help history
     3  2006-10-25_20:48:14help fc
     4  2006-10-25_20:48:18history
     5  2006-10-25_20:48:39export HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S'
     6  2006-10-25_20:48:41history

  \# Better
  bash-3.00# HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S; '
  bash-3.00# history
     1  2006-10-25_20:48:04; ls -la
     2  2006-10-25_20:48:11; help history
     3  2006-10-25_20:48:14; help fc
     4  2006-10-25_20:48:18; history
     5  2006-10-25_20:48:39; export HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S'
     6  2006-10-25_20:48:41; history
     7  2006-10-25_20:48:47; HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S; '
     8  2006-10-25_20:48:48; history

  \# Getting tricky now
  bash-3.00# HISTTIMEFORMAT=': %Y-%m-%d_%H:%M:%S; '
  bash-3.00# history
     1  : 2006-10-25_20:48:04; ls -la
     2  : 2006-10-25_20:48:11; help history
     3  : 2006-10-25_20:48:14; help fc
     4  : 2006-10-25_20:48:18; history
     5  : 2006-10-25_20:48:39; export HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S'
     6  : 2006-10-25_20:48:41; history
     7  : 2006-10-25_20:48:47; HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S; '
     8  : 2006-10-25_20:48:48; history

  The last example uses the : built-in with the ; metacharacter to encapsulate the date stamp into a "do nothing" command (e.g., : 2006-10-25_20:48:48;).

  This allows you to reuse a literal line from the history file without having to bother parsing out the date stamp.

  Note the space after the : is required.
  There are also shell options to configure history-file handling.

  If histappend is set, the shell appends to the history file; otherwise it overwrites the history file.

  Note that it is still truncated to $HISTSIZE.

  If cmdhist is set, multiline commands are saved as a sin- gle line, with semicolons added as needed.

  If lithist is set, multiline commands are saved with embedded newlines.

  Using History
  As we discovered in Chapter 1, bash maintains a history of commands that have been entered.

  This list of commands is kept in your home directory in a file called .bash_history.

  The history facility is a useful resource for redu- cing the amount of typing you have to do, especially when combined with command-line editing.
  Advanced Keyboard Tricks 73
  Searching History
  At any time, we can view the contents of the history list:
  [me@linuxbox ~]$ history | less
  By default, bash stores the last 500 commands you have entered.

  We will see how to adjust this value in Chapter 11.

  Let’s say we want to find the com- mands we used to list /usr/bin.

  Here is one way we could do this:
  [me@linuxbox ~]$ history | grep /usr/bin
  And let’s say that among our results we got a line containing an interest-
  ing command like this:
     88  ls -l /usr/bin > ls-output.txt
  The number 88 is the line number of the command in the history list.

  We could use this immediately with another type of expansion called history expansion.

  To use our discovered line, we could do this:
  [me@linuxbox ~]$ !88
  bash will expand !88 into the contents of the 88th line in the history list.

  We will cover other forms of history expansion a little later.
  bash also provides the ability to search the history list incrementally.

  This means that we can tell bash to search the history list as we enter characters, with each additional character further refining our search.

  To start an incre- mental search, enter CTRL-R followed by the text you are looking for.

  When you find it, you can either press ENTER to execute the command or press CTRL-J to copy the line from the history list to the current command line.

  To find the next occurrence of the text (moving "up" the history list), press CTRL-R again.

  To quit searching, press either CTRL-G or CTRL-C.

  Here we see it in action:
  [me@linuxbox ~]$
  First press CTRL-R:
  (reverse-i-search)`':
  The prompt changes to indicate that we are performing a reverse incre- mental search.

  It is "reverse" because we are searching from "now" to some time in the past.

  Next, we start typing our search text, which in this example is /usr/bin:
  (reverse-i-search)`/usr/bin': ls -l /usr/bin > ls-output.txt
                74 Chapter 8
  Immediately, the search returns its result.

  Now we can execute the command by pressing ENTER, or we can copy the command to our current command line for further editing by pressing CTRL-J.

  Let’s copy it.

  Press CTRL-J:
  [me@linuxbox ~]$ ls -l /usr/bin > ls-output.txt
  Our shell prompt returns, and our command line is loaded and ready for action!

  Table 8-5 lists some of the keystrokes used to manipulate the history list.

  CTRL-P Move to the previous history entry.
  Same action as the up arrow.

  CTRL-N Move to the next history entry.
  Same action as the down arrow.

  ALT-< Move to the beginning (top) of the history list.
  ALT-> Move to the end (bottom) of the history list; i.e., the current command line.

  CTRL-R Reverse incremental search.
  Searches incrementally from the current command line up the history list.

  ALT-P Reverse search, non-incremental.

  With this key, type the search string and press ENTER before the search is performed.
  ALT-N Forward search, non-incremental.

  CTRL-O Execute the current item in the history list and advance to the next one.

  This is handy if you are trying to re-execute a sequence of commands in the history list.

  History Expansion

  The shell offers a specialized type of expansion for items in the history list by using the ! character.

  We have already seen how the exclamation point can be followed by a number to insert an entry from the history list.

  There are a number of other expansion features (see Table 8-6).
  I would caution against using the !string and !?string forms unless you are absolutely sure of the contents of the history list items.
  Many more elements are available in the history expansion mechanism, but this subject is already too arcane and our heads may explode if we con- tinue.

  The "HISTORY EXPANSION" section of the bash man page goes into all the gory details.

  Table 8-6: History Expansion Commands

  Sequence Action
  !! Repeat the last command.

  It is probably easier to press the up arrow and ENTER.
  !number Repeat history list item number.
  !string Repeat last history list item starting with string.
  !?string Repeat last history list item containing string.


### VO 300w

  *history

  The history command lists the saved commands, each with an identifying number.

  $ history 20

  shows your last 20 commands

  *filter

  $ history | head
  $ history | tail
  $ history | grep

  *search

  To start an incre- mental search, enter CTRL-R followed by the text you are looking for.

  When you find it, you can either press ENTER to execute the command or press CTRL-J to copy the line from the history list to the current command line.

  To find the next occurrence of the text (moving "up" the history list), press CTRL-R again.

  To quit searching, press either CTRL-G or CTRL-C.

  [me@linuxbox ~]$ ls

  First press CTRL-R:

  Now we can execute the command by pressing ENTER

  *expansion

  !$  means "take the last thing on the previous command line

  !number Repeat history list item number

  SD:
  * !string Repeat last history list item starting with string.
  * !?string Repeat last history list item containing string.

  Other expansions available; never needed them - simply edit history.

  *configuration

  Increasing $HISTSIZE may be useful, and unsetting it causes the $HISTFILE length to be unlimited.

  $HISTFILE

  The $HISTSIZE variable sets the number of lines permit- ted in the history stack in memory.

  $HISTIGNORE and $HISTCONTROL control what goes into your history in the first place.

  $HISTIGNORE is more flexible since it allows you to specify patterns to decide what command lines to save to the history.

  $HISTCONTROL is more limited in that it sup- ports only the few keywords listed here (any other value is ignored):

  ignorespace
  Command lines that begin with a space character are not saved in the history list.

  ignoredups
  Command lines that match the previous history entry are not saved in the his- tory list.

  ignoreboth
  Shorthand for both ignorespace and ignoredups.

  erasedups
  All previous command lines that match the current line are removed from the history list before that line is saved.

  $HISTTIMEFORMAT. strftime format string to use when displaying or writing the history.

  bash-3.00# HISTTIMEFORMAT=': %Y-%m-%d_%H:%M:%S; '
  bash-3.00# history
  4  : 2006-10-25_20:48:18; history
  5  : 2006-10-25_20:48:39; export HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S'
  6  : 2006-10-25_20:48:41; history
  7  : 2006-10-25_20:48:47; HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S; '
  8  : 2006-10-25_20:48:48; history


