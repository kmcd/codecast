## Intro 1m

## Getting help 2m

man COMMAND
* scroll
* search
man -k
help
man hier

man—Display a command’s manual page.

Most executable programs intended for command-line use provide a formal piece of documentation called a manual or man page. A special paging pro- gram called man is used to view them, like this:

man program

where program is the name of the command to view.

Man pages vary somewhat in format but generally contain a title, a syn-
opsis of the command’s syntax, a description of the command’s purpose, and a listing and description of each of the command’s options. Man pages, however, do not usually include examples, and they are intended as a refer- ence, not a tutorial. As an example, let’s try viewing the man page for the ls command:

[me@linuxbox ~]$ man ls
On most Linux systems, man uses less to display the manual page, so all of the familiar less commands work while displaying the page.

The “manual” that man displays is broken into sections and covers not only user commands but also system administration commands, program- ming interfaces, file formats, and more. Table 5-1 describes the layout of the manual.

Table 5-1: Man Page Organization
 Section
1 2 3 4 5 6 7 8
Contents
User commands
Programming interfaces for kernel system calls Programming interfaces to the C library Special files such as device nodes and drivers File formats
Games and amusements such as screensavers Miscellaneous
System administration commands

Sometimes we need to look in a specific section of the manual to find what we are looking for. This is particularly true if we are looking for a file format that is also the name of a command. If we don’t specify a section num- ber, we will always get the first instance of a match, probably in section 1. To specify a section number, we use man like this:

man section search_term For example:
[me@linuxbox ~]$ man 5 passwd

will display the man page describing the file format of the /etc/passwd file.

--help—Display Usage Information

Many executable programs support a --help option that displays a descrip- tion of the command’s supported syntax and options. For example:

[me@linuxbox ~]$ mkdir --help

Some programs don’t support the --help option, but try it anyway. Often it results in an error message that will reveal the same usage information.

help—Get Help for Shell Builtins

bash has a built-in help facility for each of the shell builtins. To use it, type help followed by the name of the shell builtin. For example:

[me@linuxbox ~]$ help cd
cd: cd [-L|-P] [dir]

A note on notation: When square brackets appear in the description of a command’s syntax, they indicate optional items. A vertical bar character indicates mutually exclusive items. An example is the cd command above: cd [-L|-P] [dir].

This notation says that the command cd may be followed optionally by either a -L or a -P and further, optionally followed by the argument dir.

Self-directed:

apropos—Display a list of appropriate commands.
whatis—Display a very brief description of a command.
info—Display a command’s info entry.

## Shell environment 4m

A command can be one of four things:

  An executable program like all those files we saw in /usr/bin. Within this category, programs can be compiled binaries, such as programs written in C and C++, or programs written in scripting languages, such as the shell, Perl, Python, Ruby, and so on.

  A command built into the shell itself. bash supports a number of com- mands internally called shell builtins. The cd command, for example, is a shell builtin.

  A shell function. Shell functions are miniature shell scripts incorporated into the environment. We will cover configuring the environment and writing shell functions in later chapters, but for now just be aware that they exist.

  An alias. An alias is a command that we can define ourselves, built from other commands.

type—Indicate how a command name is interpreted.
which—Display which executable program will be executed.

Identifying Commands

It is often useful to know exactly which of the four kinds of commands is being used, and Linux provides a couple of ways to find out.
type—Display a Command’s Type

The type command is a shell builtin that displays the kind of command the shell will execute, given a particular command name. It works like this:
type command
where command is the name of the command you want to examine. Here are
some examples:

[me@linuxbox ~]$ type type
type is a shell builtin

[me@linuxbox ~]$ type ls
ls is aliased to ls --color=tty'

[me@linuxbox ~]$ type cp
cp is /bin/cp

Here we see the results for three different commands. Notice that the ls command (taken from a Fedora system) is actually an alias for the ls com- mand with the --color=tty option added. Now we know why the output from ls is displayed in color!

which—Display an Executable’s Location

Sometimes more than one version of an executable program is installed on a system. While this is not very common on desktop systems, it’s not unusual on large servers. To determine the exact location of a given executable, the which command is used:

[me@linuxbox ~]$ which ls /bin/ls
which works only for executable programs, not builtins or aliases that are substitutes for actual executable programs. When we try to use which on a shell builtin (for example, cd), we get either no response or an error message:
[me@linuxbox ~]$ which cd
/usr/bin/which: no cd in (/opt/jre1.6.0_03/bin:/usr/lib/qt-3.3/bin:/usr/kerber os/bin:/opt/jre1.6.0_03/bin:/usr/lib/ccache:/usr/local/bin:/usr/bin:/bin:/home /me/bin)
This is a fancy way of saying “command not found.”

A login bash will read .bash_profile , .bash_login , or .profile . A bash subshell - but not a login shell - will read a file named .bashrc in your home directory.

The difference between *environment variables* and regular shell variables ( 6.8 ) is that a shell variable is local to a particular instance of the shell (such as a shell script), while environment variables are "inherited" by any program you start, including another shell ( 38.4 ) . That is, the new process gets its own copy of these variables, which it can read, modify, and pass on in turn to its own children. In fact, every UNIX process (not just the shell) passes its environment variables to its child processes.

echo $TERM
echo $PWD
echo $HOME

Many UNIX utilities, including the shell, need information about you and what you're doing in order to do a reasonable job.

Lots of UNIX programs (like mail programs) include a command to start an editor as a subprocess; they like to know your favorite editor. And so on.

*alias* define abbreviations for commonly used commands

alias g='git '
alias h='history | grep '
alias j='open -a /Applications/jEdit.app '
alias jpf='j ~/.bash_profile'
alias ls='ls -Gp '
alias rbd='open ~/Documents/tech/ruby2.0_rdoc/index.html '
alias rl='source ~/.bash_profile'
alias rrd='open ~/Documents/tech/rails4_rdoc/index.html '
alias rrg='open http://guides.rubyonrails.org'
alias rrl='tail -f log/guard.log log/development.log'
alias rsr='ka ruby; ka _test; nohup bundle exec guard > log/guard.log &'
alias td='j ~/.todo.txt'
alias tree='tree -C '
alias wf='ghi list -L bug; ghi list -M 2 -N bug'

$ unalias rm
$ alias

functions

bug () { ghi open -m "$1" -L bug ; }
feature () { ghi open -m "$1" -L feature ; }
ka () { ps waux | grep $1 | awk '{print $2}' | xargs kill -9 ; }
jo () {  j `find . -name "$*"` ; }

The spaces and the semicolon ( ; ) are both important!

The "$@" ( 44.15 ) is replaced by the command-line arguments (other options, or directory and filenames), if you use any:

the shell will replace that string with a quoted ( 8.14 ) set of the script's command-line arguments. Then you can pass as many arguments as you want, including pathnames with unusual characters

You have a stash of personal utilities you like to use, but you are not root on the sys- tem and can’t place them into the normal locations like /bin or /usr/local/bin, or there is some other reason to separate them.

$ PATH="$PATH:~/bin"

Now if dot were listed first, then someone else’s version of ls would supersede the normal ls command and you might unwit- tingly run that command. Don’t believe us? Try this:

$ bash
$ cd
$ touch ls
$ chmod 755 ls
$ PATH=".:$PATH"
$ ls
$

## Keyboard shortcuts 2m

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

We know, for example, that the arrow keys move the cursor, but there are many more features. 

Think of these as additional tools that we can employ in our work. 

It’s not important to learn all of them, but many of them are very useful. 

Pick and choose as desired.
Note: Some of the key sequences below (particularly those that use the ALT key) may be inter- cepted by the GUI for other functions. 

All of the key sequences should work properly when using a virtual console.
Cursor Movement
Table 8-1 lists the keys used to move the cursor.
Table 8-1: Cursor Movement Commands
Key Action
CTRL-A Move cursor to the beginning of the line.
CTRL-E Move cursor to the end of the line.
CTRL-F Move cursor forward one character; same as the right arrow key.
CTRL-B Move cursor backward one character; same as the left arrow key.
ALT-F Move cursor forward one word.
ALT-B Move cursor backward one word.
CTRL-L Clear the screen and move the cursor to the top left corner. 

The clear command does the same thing.
Modifying Text
Table 8-2 lists keyboard commands that are used to edit characters on the command line.
Cutting and Pasting (Killing and Yanking) Text
The Readline documentation uses the terms killing and yanking to refer to what we would commonly call cutting and pasting. 

Table 8-3 lists the com- mands for cutting and pasting. 

Items that are cut are stored in a buffer called the kill-ring.

Table 8-2: Text Editing Commands
Key Action
CTRL-D Delete the character at the cursor location.
CTRL-T Transpose (exchange) the character at the cursor location with the one preceding it.
ALT-T Transpose the word at the cursor location with the one pre ceding it.
ALT-L Convert the characters from the cursor location to the end of the word to lowercase.
ALT-U Convert the characters from the cursor location to the end of the word to uppercase.
Table 8-3: Cut and Paste Commands
Key Action
CTRL-K Kill text from the cursor location to the end of line.
CTRL-U Kill text from the cursor location to the beginning of the line. 

ALT-D Kill text from the cursor location to the end of the current word.
ALT-BACKSPACE Kill text from the cursor location to the beginning of the cur rent word. 

If the cursor is at the beginning of a word, kill the
previous word.
CTRL-Y Yank text from the kill-ring and insert it at the cursor location.
                          THE META KEY
If you venture into the Readline documentation, which can be found in the “READLINE” section of the bash man page, you will encounter the term meta key. 

On modern keyboards this maps to the ALT key, but it wasn’t always so.
Back in the dim times (before PCs but after Unix) not everybody had their own computer. 

What they might have had was a device called a terminal. 

A ter- minal was a communication device that featured a text-display screen and a keyboard and had just enough electronics inside to display text characters and move the cursor around. 

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

For completion to be successful, the “clue” you give it has to be unambiguous. 

We can go further:
[me@linuxbox ~]$ ls Do Then press TAB:
[me@linuxbox ~]$ ls Documents
The completion is successful.
              72 Chapter 8
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

You can see a list in the bash man page under the “READLINE” section.

line-kill character - typically CTRL-u o

"word-erase" character, usually CTRL-w, which deletes only back to the previous whitespace

TAB filename completion

CTL + L clear
CTL + D exit
CTL + C cancel/quit

 9.5 Build Strings with { }

I've been finding more and more uses for the {} pattern-expansion characters in csh , tcsh , and bash . (Other shells can use {} , too; see article 15.3 .) They're similar to * , ? , and [] ( 15.2 ) , but they don't match filenames the way that * , ? , and [] do. You can give them arbitrary text (not just filenames) to expand - that "expand-anything" ability is what makes them so useful.

Here are some examples to get you thinking:

To fix a typo in a filename (change fixbold5.c to fixbold6.c ):

    % 

    mv fixbold{5,6}.c

An easy way to see what the shell does with {} is by adding echo ( 8.6 ) before the mv :

    % 

    echo mv fixbold{5,6}.c


    mv fixbold5.c fixbold6.c

To copy filename to filename.bak in one easy step:

    % 

    cp filename{,.bak}

To print files from other directory(s) without retyping the whole pathname:

    % 

    lpr /usr3/hannah/training/{ed,vi,mail}/lab.{ms,out}

That would give lpr ( 43.2 ) all of these files:

    /usr3/hannah/training/ed/lab.ms
    /usr3/hannah/training/ed/lab.out
    /usr3/hannah/training/vi/lab.ms
    /usr3/hannah/training/vi/lab.out
    /usr3/hannah/training/mail/lab.ms
    /usr3/hannah/training/mail/lab.out

...in one fell swoop!

To edit ten new files that don't exist yet:

    % 

    vi /usr/foo/file{a,b,c,d,e,f,g,h,i,j}

That would make /usr/foo/filea , /usr/foo/fileb , ... /usr/foo/filej . Because the files don't exist before the command starts, the wildcard vi   /usr/foo/file[a-j] would not work ( 9.4 ) .

An easy way to step through three-digit numbers 000, 001, ..., 009, 010, 011, ..., 099, 100, 101, ... 299 is:



foreach
 

  


foreach n ({0,1,2}{0,1,2,3,4,5,6,7,8,9}{0,1,2,3,4,5,6,7,8,9})
   ...
Do whatever with the number $n
...
end

Yes, csh also has built-in arithmetic, but its @ operator ( 47.4 ) can't make numbers with leading zeros. This nice trick shows that the {} operators are good for more than just filenames.

To create sets of subdirectories:

    % 

    mkdir man


    % 

    mkdir man/{man,cat}{1,2,3,4,5,6,7,8}


    % 

    ls -F man


    cat1/   cat3/   cat5/   cat7/   man1/   man3/   man5/   man7/
    cat2/   cat4/   cat6/   cat8/   man2/   man4/   man6/   man8/

To print ten copies of the file project_report (if your lpr ( 43.2 ) command doesn't have a -#10 option):

    % 

    lpr project_repor{t,t,t,t,t,t,t,t,t,t}



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

As of bash version 3, there is a fascinating new variable called $HISTTIMEFORMAT. If set and non-null, it specifies an strftime format string to use when displaying or writing the history. If you don’t have bash version 3, but you do use a terminal with a scroll- back buffer, adding a date and time stamp to your prompt can also be very helpful. See Recipe 16.2, “Customizing Your Prompt.” Watch out because stock bash does not put a trailing space after the format, but some systems (e.g., Debian) have patched it to do so:

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
   
The last example uses the : built-in with the ; metacharacter to encapsulate the date stamp into a “do nothing” command (e.g., : 2006-10-25_20:48:48;). 

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

To find the next occurrence of the text (moving “up” the history list), press CTRL-R again. 

To quit searching, press either CTRL-G or CTRL-C. 

Here we see it in action:
[me@linuxbox ~]$
First press CTRL-R:
(reverse-i-search)`':
The prompt changes to indicate that we are performing a reverse incre- mental search. 

It is “reverse” because we are searching from “now” to some time in the past. 

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
Table 8-5: History Commands
Key Action
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

The “HISTORY EXPANSION” section of the bash man page goes into all the gory details. 

Table 8-6: History Expansion Commands

Sequence Action
!! Repeat the last command. 

It is probably easier to press the up arrow and ENTER.
!number Repeat history list item number.
!string Repeat last history list item starting with string. 

!?string Repeat last history list item containing string.

## Directory navigation 4m


## Displaying files 4m
## File search 4m
## File modification 2m
## Text processing 4m
## Networking 2m
## Processes 4m
## Package management 2m
## OUTRO 1m
