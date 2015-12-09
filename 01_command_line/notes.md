# Outline
## Intro 1m

  Title
  Time required
  Required materials
  Presumed knowledge
    * cp,mv,cd,rm
  behavioral/knowledge objectives
    * Two or three interesting but relevant questions
    * Showing a picture/s, a chart or a model
    * A situation Statement of Aim: Announcement of the statement of the lesson in a clear, concise, like this "Today, we shall study the..."

## Getting help 2m

  Instruction:
  * man
  * man -k
  * help

  Self-directed:
  * info

  Evaluation:
  * find out how to X

## Shell environment 2m

  ~/.bashrc
  variables, e.g. $EDITOR
  ~/bin, $PATH
  aliases
  functions (show with type)

  Chapter 6: Shell and Environment Variables
  1.6 Shell quoting

  Aliases ( 10.2 )
  Shell functions ( 10.9 )
  16.9 Keeping a Private Stash of Utilities by Adding ~/bin

  Self-directed
  * prompt customisation
  * create a desk clone (later with find?)

  Evaluation
  * Create an alias for X

  9.16  backquotes ( ` ` ) does command substitution
  Process substitution ( 9.18 )

## History 2m

  Chapter 11: The Lessons of History
  16.12 Setting Shell History Options
  106 Using History

## Keyboard speed 2m

  Faster erasing ( 9.2 )
  Filename completion ( 9.8 , 9.9 , 9.10 )
  102 Command Line Editing
  clear
  exit

## Pattern expansion 2m

  9.5 Build Strings with { }

## Directory navigation 2m

  e.g. Rails source

  pwd, cd, ls
  file globbing/wildcards
  ls -R
  tree
  man hier (file system layout)
  /Volumes see: OSX page
  df

  export CC_CLI=DIR
  cd $CC_CLI
  alias cdc="cd DIR"

  Chapter 9: Saving Time on the Command Line

  Chapter 15: Wildcards (split into two sections?)

## Wildcards 4m
## File display 2m

  e.g. Rails source

  cat
  less
  (syntax highlight)
  du/df
  wc?
  head / tail
  open

  Chapter 25: Showing What's in a File
  59 Calculating File Size and Disk Space
  165 Launching GUI Applications

## File search 4m

  e.g. Rails source

  find
  locate
  mdfind
  grep / ack (Basic regex)

  Chapter 17: Finding Files with find
  Chapter 27: Searching Through Files

  19.15 Shell wildcards vs. Regular expressions

  128 Shining a Light on Spotlight

  9.1 Finding All Your MP3 Files
  9.2 Handling Filenames Containing Odd Characters
  9.5 Finding Files Irrespective of Case
  9.6 Finding Files by Date
  9.7 Finding Files by Type
  9.9 Finding Files by Content
  9.8 Finding Files by Size

  103 Shell games
  219 Searching for files

## File modification 2m
  (CRUD)

  cp *-dt-*-nt-~
  cp foo.{txt,md}
  ln
  chown (permissions)
  chmod
  touch
  tar / gzip

  Chapter 13: Redirecting Input and Output
  http://docstore.mik.ua/orelly/unix/upt/ch25_02.htm
  Chapter 22: File Security, Ownership, and Sharing
  17.1 Renaming Many Files
  109 Permissions

## Text processing 4m

  awk
  xargs
  cmp / diff
  cut
  sort
  uniq
  sed
  for/while loop

  Chapter 34: The sed Stream Editor
  Chapter 36: Sorting

  8.1 Sorting Your Output
  8.2 Sorting Numbers
  8.4 Cutting Out Parts of Your Output
  8.5 Removing Duplicate Lines
  8.9 Translating Characters

  141 Pipes and Filters

  265 Text processing

  4.3 Running Several Commands in Sequence
  4.4 Running Several Commands All at Once
  4.10 Running All Scripts in a Directory (loop)
  2.14 Saving or Grouping Output from Several Commands

  211 Command Line

  Command line substitution : ` ` or $() (in pipe section)

## Networking 2m

  ftp
  curl / wget / httrack
  ssh
  scp
  SSH config
  lsof
  ifconfig

  176 Transferring Files
  207 Networking

## Processes 4m

  e.g. Rails develeopment: start/stop server, background jobs

  Chapter 12: Job Control
  ps / pstree
  top / htop / activity monitor
  job control: bg, fg
  kill / killall
  nohup
  at
  cron
  cron format
  Deamon processes
  init
  OSX launchctl

  Job control ( 12.1 )

  Chapter 38: Starting, Stopping, and Killing Processes
  Chapter 39: Time and Performance
  Chapter 40: Delayed Execution

  154 Running a Command in the Background
  155 Checking on a Process
  162 Canceling a Process

  127 Processes

## Package management 2m

  (Move to start?)

  e.g. install cheat
  e.g. install PostgreSQL 9.3

  brew install ...
  install home brew
  find app
  install app
  boot config
  taps/custom
  xcode-select -p
  xcode-select --install
  remove app
  ruby/prog lang env

  http://coolestguidesontheplanet.com/installing-homebrew-os-x-yosemite-10-10-package-manager-unix-apps/

## OUTRO 1m

  List behavioral/knowledge objectives
  Recap
  Further reading

  # REFERENCE

# Reference
## Links
  * http://blog.sanctum.geek.nz/series/unix-as-ide/
  * http://www.ee.surrey.ac.uk/Teaching/Unix/unix5.html
  * http://blog.sanctum.geek.nz/series/unix-as-ide/
  * http://lifehacker.com/eight-terminal-utilities-every-os-x-command-line-user-s-1593793109
  * http://www.learnenough.com/command-line-tutorial

## UNIX Power Tools

  Faster erasing ( 9.2 )
  Filename completion ( 9.8 , 9.9 , 9.10 )
  Build Strings with { }
  9.16  backquotes ( ` ` ) does command substitution
  Process substitution ( 9.18 )
  xargs http://docstore.mik.ua/orelly/unix/upt/ch09_21.htm
  Job control ( 12.1 )
  Aliases ( 10.2 )
  Shell functions ( 10.9 )

  Chapter 2: Logging In
  Chapter 5: Setting Up Your Terminal
  Chapter 6: Shell and Environment Variables
  Chapter 7: Setting Your Shell Prompt
  Chapter 9: Saving Time on the Command Line
  Chapter 10: Aliases
  Chapter 11: The Lessons of History
  Chapter 12: Job Control
  Chapter 13: Redirecting Input and Output
  Chapter 15: Wildcards
  Chapter 17: Finding Files with find
  Chapter 22: File Security, Ownership, and Sharing
  Chapter 25: Showing What's in a File
  Chapter 27: Searching Through Files
  Chapter 34: The sed Stream Editor
  Chapter 36: Sorting
  Chapter 38: Starting, Stopping, and Killing Processes
  Chapter 39: Time and Performance
  Chapter 40: Delayed Execution

## Bash cookbook

  1.6 Shell quoting
  2.14 Saving or Grouping Output from Several Commands
  4.1 Running Any Executable
  4.3 Running Several Commands in Sequence
  4.4 Running Several Commands All at Once
  4.10 Running All Scripts in a Directory (loop)
  8.1 Sorting Your Output
  8.2 Sorting Numbers
  8.4 Cutting Out Parts of Your Output
  8.5 Removing Duplicate Lines
  8.9 Translating Characters
  9.1 Finding All Your MP3 Files
  9.2 Handling Filenames Containing Odd Characters
  9.5 Finding Files Irrespective of Case
  9.6 Finding Files by Date
  9.7 Finding Files by Type
  9.9 Finding Files by Content
  9.8 Finding Files by Size
  16.2 Customizing Your Prompt
  16.9 Keeping a Private Stash of Utilities by Adding ~/bin
  16.12 Setting Shell History Options
  17.1 Renaming Many Files
  17.6 Logging an Entire Session or Batch Job
  17.15 Using sudo on a Group of Commands
  19.15 Shell wildcards vs. Regular expressions

## UNIX for OSX

  59 Calculating File Size and Disk Space
  128 Shining a Light on Spotlight
  135 Standard Input and Standard Output
  141 Pipes and Filters
  154 Running a Command in the Background
  155 Checking on a Process
  162 Canceling a Process
  165 Launching GUI Applications
  176 Transferring Files

## Prag prog

  103 Shell games

## Productive Programmer

  211 Command Line

## The Linux Command Line

  102 Command Line Editing
  106 Using History
  109 Permissions
  127 Processes
  207 Networking
  219 Searching for files
  265 Text processing



# Chapter notes
## Intro 1m
  Every woodworker needs a good, solid, reliable workbench, somewhere to hold work pieces at a convenient height while he or she works them. The workbench becomes the center of the wood shop, the craftsman returning to it time and time again as a piece takes shape.

  For a programmer manipulating files of text, that workbench is the command shell. From the shell prompt, you can invoke your full repertoire of tools, using pipes to combine them in ways never dreamt of by their original developers. From the shell, you can launch applications, debuggers, browsers, editors, and utilities. You can search for files, query the status of the system, and filter output. And by programming the shell, you can build complex macro commands for activities you perform often.
  For programmers raised on GUI interfaces and integrated development environments (IDEs), this might seem an extreme position. After all, can't you do everything equally well by pointing and clicking?
  The simple answer is "no." GUI interfaces are wonderful, and they can be faster and more convenient for some simple operations. Moving files, reading MIME-encoded e-mail, and typing letters are all things that you might want to do in a graphical environment. But if you do all your work using GUIs, you are missing out on the full capabilities of your environment. You won't be able to automate common tasks, or use the full power of the tools available to you. And you won't be able to combine your tools to create customized macro tools. A benefit of GUIs is WYSIWYG—what you see is what you get. The disadvantage is WYSIAYG—what you see is all you get.
  GUI environments are normally limited to the capabilities that their designers intended. If you need to go beyond the model the designer provided, you are usually out of luck—and more often than not, you do need to go beyond the model. Pragmatic Programmers don't just cut code, or develop object models, or write documentation, or automate the build process—we do all of these things. The scope of any one tool is usually limited to the tasks that the tool is expected to perform. For instance, suppose you need to integrate a code preprocessor (to implement design-by-contract, or multi-processing pragmas, or some such) into your IDE. Unless the designer of the IDE explicitly provided hooks for this capability, you can't do it.
  You may already be comfortable working from the command prompt, in which case you can safely skip this section. Otherwise, you may need to be convinced that the shell is your friend.
  As a Pragmatic Programmer, you will constantly want to perform ad hoc operations—things that the GUI may not support. The command line is better suited when you want to quickly combine a couple of commands to perform a query or some other task. Here are a few examples.

  Find all .c files modified more recently than your Makefile.
  Shell...
  find . -name ' *.c' -newer Makefile -print


    GUI.....
  Open the Explorer, navigate to the correct directory, click on the Makefile, and note the modification time. Then bring up Tools/Find, and enter *.c for the file specification. Select the date tab, and enter the date you noted for the Makefile in the first date field. Then hit OK.

  Shell...
  zip archive.zip *.h *.c -or- tar cvf archive.tar *.h *.c
  GUI.....
  Bring up a ZIP utility (such as the shareware WinZip [URL41], select "Create New Archive," enter its name, select the source directory in the add dialog, set the filter to "* .c", click "Add," set the filter to "* .h", click "Add," then close the archive. ̈

  Shell...
  find . -name '*.java' -mtime +7 -print
  GUI.....
  Click and navigate to "Find files," click the "Named" field and type in "*.java", select the "Date Modified" tab. Then select "Between." Click on the starting date and type in the starting date of the beginning of the project. Click on the ending date and type in the date of a week ago today (be sure to have a calendar handy). Click on "Find Now."
  Shell...
  find . -name '*.java' -mtime +7 -print |
       xargs grep 'java.awt'
  GUI.....
  Load each file in the list from the previous example into an editor and search for the string "java.awt". Write down the name of each file containing a match.
   Construct a zip/tar archive of my source.
  Which Java files have not been changed in the last week?
  Of those files, which use the awt libraries?
  Clearly the list could go on. The shell commands may be obscure or terse, but they are powerful and concise. And, because shell commands can be combined into script files (or command files under Windows systems), you can build sequences of commands to automate things you do often.
### VO 300w

  PROMO

  FORTHCOMING

  Show you how to:
  * get help from manual pages
  * use keyboard shortcuts
  * navigate & understand file system
  * use history
  *

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

  The "manual" that man displays is broken into sections and covers not only user commands but also system administration commands, program- ming interfaces, file formats, and more. Table 5-1 describes the layout of the manual.

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

  --help —Display Usage Information

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
  man -k

  whatis—Display a very brief description of a command.
  info—Display a command’s info entry.

### VO 300w

  OJ
  * get help
  * search for man pages
  * understand man page format
  * search within a man page
  * getting help when no man pages available

  To search the available manual pages, type

  $ man -k

  You know the ls command list's a directory contents.

  (?)
  $ a TAB
  $ whatis a2p

  Let's add nice color output to your directory listing

  $ man ls

  To scroll in a manual page, type

  Enter CTRL+U to Scroll UP
  Enter CTRL+D to Scroll DOWN
  Enter / to search
  Enter n to go forward
  Enter N to go back
  Enter - to toggle case sensitive search

  $ man less

  Some programs don’t support the --help option, but try it anyway. Often it results in an error message that will reveal the same usage information.

  bash has a built-in help facility for each of the shell builtins. To use it, type help followed by the name of the shell builtin. For example:

  [me@linuxbox ~]$ help cd
  cd: cd [-L|-P] [dir]

  square brackets indicate optional items.
  A vertical bar character indicates mutually exclusive items.

  the command cd may be followed optionally by either a -L or a -P and further, optionally followed by the argument dir.

  SLIDE: Man Page Organization
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

  Man pages, usually don't have examples, and they are intended as a refer ence, not a tutorial. Install cheat (skip to section) for examples:

  cheat ls

  RC:
  * search for man pages
  * understand man page format
  * search within a man page
  * getting help when no man pages available

  EV:
  * search for X man page
  * within a man page X, search for Y
  * find 2 sections for crontab

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
  This is a fancy way of saying "command not found."

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
  jo () {  j ` find . -name "$*" ` ; }

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

  sudo—Execute a Command as Another User

  The sudo command is like su in many ways but has some important addi- tional capabilities. The administrator can configure sudo to allow an ordin- ary user to execute commands as a different user (usually the superuser) in a very controlled way. In particular, a user may be restricted to one or more specific commands and no others. Another important difference is that the use of sudo does not require access to the superuser’s password. To authen- ticate using sudo, the user enters his own password. Let’s say, for example, that sudo has been configured to allow us to run a fictitious backup program called backup_script, which requires superuser privileges.

  With sudo it would be done like this:

  [me@linuxbox ~]$ sudo backup_script Password:

  System Backup Starting...

  After entering the command, we are prompted for our password (not the superuser’s), and once the authentication is complete, the specified command is carried out. One important difference between su and sudo is that sudo does not start a new shell, nor does it load another user’s environ- ment. This means that commands do not need to be quoted any differently than they would be without using sudo. Note that this behavior can be over- ridden by specifying various options. See the sudo man page for details.
  To see what privileges are granted by sudo, use the -l option to list them:
  [me@linuxbox ~]$ sudo -l
  User me may run the following commands on this host:
  (ALL) ALL

  9.16  backquotes ( ` ` ) does command substitution
  Process substitution ( 9.18 )

   < ( process )
   `\`
   $()

### VO 300w

  *bash_profile

  A login bash will read .bash_profile , .bash_login , or .profile . A bash subshell - but not a login shell - will read a file named .bashrc in your home directory.

  .bashrc mention?

  EDITOR ~/.bash_profile
  source ~/.bash_profile

  *export

  Many UNIX utilities, including the shell, need information about you and what you're doing in order to do a reasonable job.

  e.g. git $EDITOR

  a shell variable is local to a particular instance of the shell (such as a shell script) environment variables are "inherited" by any program you start, including another shell

  echo $TERM
  echo $PWD
  echo $HOME

  *export PATH

  You have a stash of personal utilities you like to use, but you are not root on the sys- tem and can’t place them into the normal locations like /bin or /usr/local/bin, or there is some other reason to separate them.

  $ PATH="$PATH:~/bin"

  *commands

  An executable program: compiled binaries or interpreted scripting languages, such as the shell, Perl, Python, Ruby, and so on

  $ ls /usr/bin

  A command built into the shell itself; e.g. cd

  $ man bash
  $ help
  $ help cd

  *alias

  An alias. An alias is a command that we can define ourselves, built from other commands.

  define abbreviations for commonly used commands

  alias ls='ls -Gp '
  alias ll='ls -lahGp '
  alias g='git '

  alias rl='source ~/.bash_profile'

  *functions

  A shell function: takes args, executes, returns ouput

  feature () { ghi open -m "$1" -L feature ; }
  jo () {  j ` find . -name "$*" ` ; }

  The "$@" ( 44.15 ) is replaced by the command-line arguments (other options, or directory and filenames), if you use any:

  the shell will replace that string with a quoted ( 8.14 ) set of the script's command-line arguments. Then you can pass as many arguments as you want, including pathnames with unusual characters

  *self-directed
  * prompt customisation export PS1="\[\e[34;1m\]\w\[\e[0m\] $ "
  * create a desk clone

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

## Pattern expansion 2m
  9.5 Build Strings with { }

  I've been finding more and more uses for the {} pattern-expansion characters in csh , tcsh , and bash . (Other shells can use {} , too; see article 15.3 .)

  They're similar to * , ? , and [] ( 15.2 ) , but they don't match filenames the way that * , ? , and [] do.

  You can give them arbitrary text (not just filenames) to expand - that "expand-anything" ability is what makes them so useful.

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
### VO 300w
  Build Strings with pattern-expansion characters: {}

  You can give them arbitrary text (not just filenames) to expand which is very handy.

  To fix a typo in a filename (change fixbold5.c to fixbold6.c ):

  $ mv typo{5,6}.rb

  An easy way to see what the shell does with {} is by adding echo ( 8.6 ) before the mv :

  $ echo mv fixbold{5,6}.c

  mv fixbold5.c fixbold6.c

  To copy filename to filename.bak in one easy step:

  $ cp filename{,.bak}

  To print files from other directory(s) without retyping the whole pathname:

  $ lpr /usr3/hannah/training/{ed,vi,mail}/lab.{ms,out}


  /usr3/hannah/training/ed/lab.ms
  /usr3/hannah/training/ed/lab.out
  /usr3/hannah/training/vi/lab.ms
  /usr3/hannah/training/vi/lab.out
  /usr3/hannah/training/mail/lab.ms
  /usr3/hannah/training/mail/lab.out

  ...in one fell swoop!

  To edit ten new files that don't exist yet:

  $ vi /usr/foo/file{a,b,c,d,e,f,g,h,i,j}

  That would make /usr/foo/filea , /usr/foo/fileb , ... /usr/foo/filej . Because the files don't exist before the command starts, the wildcard vi   /usr/foo/file[a-j] would not work ( 9.4 ) .

  An easy way to step through three-digit numbers 000, 001, ..., 009, 010, 011, ..., 099, 100, 101, ... 299 is:

  for n in ({0,1,2}{0,1,2,3,4,5,6,7,8,9}{0,1,2,3,4,5,6,7,8,9})
  end

  Yes, csh also has built-in arithmetic, but its @ operator ( 47.4 ) can't make numbers with leading zeros. This nice trick shows that the {} operators are good for more than just filenames.

  To create sets of subdirectories:

  $ mkdir man
  $ mkdir man/{man,cat}{1,2,3,4,5,6,7,8}
  $ ls -F man

  cat1/   cat3/   cat5/   cat7/   man1/   man3/   man5/   man7/
  cat2/   cat4/   cat6/   cat8/   man2/   man4/   man6/   man8/

  To print ten copies of the file project_report command doesn't have a -#10 option):

  $ lpr project_repor{t,t,t,t,t,t,t,t,t,t}

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

### Directory navigation 2m

  pwd
  cd
  ls -R
  tree
  man hier (file system layout)
  /Volumes see: OSX page
  df

  tree

  Tree  is  a  recursive  directory  listing program that produces a depth indented listing of files, which is colorized ala dircolors if the LS_COLORS environment variable is set and output is to tty.

  With  no  arguments,  tree  lists the files in the current directory.  When directory arguments are given, tree lists all the files and/or directories found in the given  directories  each  in  turn.

  Upon  completion  of  listing  all  files/directories found, tree returns the total number of files and/or directories listed.

  By default, when a symbolic link is encountered, the path that  the  symbolic  link  refers  to  is printed after the name of the link in the format:

     name -> real-path

  If  the  \`-l'  option  is given and the symbolic link refers to an actual directory, then tree will
  follow the path of the symbolic link as if it were a real directory.

  -a     All files are printed.  By default tree does not print hidden files (those beginning with  a dot  \`.').   In  no event does tree print the file system constructs `.' (current directory)
  and \`..' (previous directory).

  -d     List directories only.

  -f     Prints the full path prefix for each file.

  -x     Stay on the current file-system only.  Ala find -xdev.

  -L level Max display depth of the directory tree.

  -P pattern
  List only those files that match the wild-card pattern.  Note: you must use the -a option to
  also  consider those files beginning with a dot `.'  for matching.  Valid wildcard operators
  are `*' (any zero or more characters), `?' (any single character), `[...]' (any single char-
  acter  listed  between  brackets (optional - (dash) for character range may be used: ex: [A-
  Z]), and `[^...]' (any single character not listed in brackets) and `|' separates  alternate
  patterns.

  -I pattern
  Do not list those files that match the wild-card pattern.

  SORTING OPTIONS
  -v     Sort the output by version.

  -r     Sort the output in reverse alphabetic order.

  -t     Sort the output by last modification time instead of alphabetically.

  -C     Turn colorization on always


  See: https://developer.apple.com/library/mac/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html

  cd
  Changes the working directory to your home directory.

  cd cd -
  Changes the working directory to the previous working directory.

  cd ~username
  Changes the working directory to the home directory of username. For example, cd ~bob changes the directory to the home directory of user bob.

  An absolute pathname begins with the root directory and follows the tree branch by branch until the path to the desired directory or file is com- pleted. For example, there is a directory on your system in which most of your system’s programs are installed. The pathname of that directory is /usr/bin. This means from the root directory (represented by the leading slash in the pathname) there is a directory called usr that contains a direct- ory called bin.

  [me@linuxbox ~]$ cd /usr/bin [me@linuxbox bin]$ pwd /usr/bin
  [me@linuxbox bin]$ ls

  Where an absolute pathname starts from the root directory and leads to its destination, a relative pathname starts from the working directory. To do this, it uses a couple of special symbols to represent relative positions in the file- system tree. These special symbols are . (dot) and .. (dot dot).


  1.16 Wildcards

  The shells provide a number of wildcards that you can use to abbreviate filenames or refer to groups of files. For example, let's say you want to delete all filenames in the current directory ( 1.21 ) ending in .txt . You could delete these files one by one, but that would be boring if there were only five and very boring if there were a hundred. Instead, you can use a wildcarded name to say, "I want all files whose names end with .txt , regardless of what the first part is." The wildcard is the "regardless" part. Like a wildcard in a poker game, a wildcard in a filename can have any value.

  The wildcard you see most often is * (asterisk), but we'll start with something simpler: ? (question mark). When it appears in a filename, the ? matches any single character. For example, letter? refers to any filename that begins with letter and has one character after that. This would include letterA , letter1 , as well as filenames with a non-printing character as their last letter, like letter ^C.

  The * wildcard matches any character or group of zero or more characters. For example, *.txt matches all files whose names end with .txt , *.c matches all files whose names end with .c (by convention, source code for programs in the C language), and so on.

  The * and ? wildcards are sufficient for 90 percent of the situations that you will find. However, there are some situations that they can't handle. For example, you may want to list files whose names end with .txt , mail , or let . There's no way to do this with a single * ; it won't let you exclude the files you don't want. In this situation, use a separate * with each filename ending:

      *.txt *mail *let

  Sometimes you need to match a particular group of characters. For example, you may want to list all filenames that begin with digits, or all filenames that begin with uppercase letters. Let's assume that you want to work with the files program. n , where n is a single-digit number. Use the filename:

      program.[0123456789]

  In other words, the wildcard [ character-list ] matches any single character that appears in the list. The character list can be any group of ASCII characters; however, if they are consecutive (e.g., A-Z, a-z, 0-9, or 3-5, for that matter), you can use a hyphen as shorthand for the range. For example, [a-zA-Z] means any alphabetic character.

  There is one exception to these wildcarding rules. Wildcards never match / , which is both the name of the filesystem root ( 1.19 ) and the character used to separate directory names in a path ( 1.21 ) .

  If you are new to computers, you probably will catch on to UNIX wildcarding quickly. If you have used any other computer system, you have to watch out for one very important detail. Virtually all computer systems except for UNIX consider a period ( . ) a special character within a filename. Many operating systems even require a filename to have a period in it. With these operating systems, a * does not match a period; you have to say *.* . Therefore, the equivalent of rm * does virtually nothing on most operating systems. Under UNIX, it is very dangerous: it means "delete all the files in the current directory, regardless of their name." You only want to give this command when you really mean it.

  But here's the exception to the exception. The shells and the ls command consider a . special if it is the first character of a filename. This is often used to hide initialization files and other files that you aren't normally concerned with; the ls command doesn't show these files unless you ask ( 16.11 ) for them. If a file's name begins with . , you always have to type the . explicitly. For example, .*rc matches all files whose names begin with . and end with rc . This is a common convention for the names of UNIX initialization files.

  Table 1-1 has a summary of the different sorts of wildcards available.
  Table 1.1: Shell Wildcard 	Matches
  ? 	Any single character
  * 	Any group of zero or more characters
  [ab] 	Either a or b
  [a-z] 	Any character between a and z, inclusive

  Wildcards can be used at any point or points within a path. Remember, wildcards only match names that already exist. You can't use them to create new files ( 9.4 ) - though some shells have curly braces ( {} ) ( 9.5 , 15.3 ) for doing that. Article 1.18 has more about how wildcards are handled.

  1.18 Who Handles Wildcards?

  Wildcards ( 1.16 ) are actually defined by the UNIX shells, rather than the UNIX filesystem. In theory, a new shell could define new wildcards, and consequently, we should discuss wildcarding when we discuss the shell. In practice, all UNIX shells (including ksh , bash , and other variants ( 1.8 ) ) honor the same wildcard conventions, and we don't expect to see anyone change the rules. (But different shells do different things when a wildcard doesn't match ( 15.4 ) .)

  You may see different wildcarding if you buy a special-purpose shell that emulates another operating system (for example, a shell that looks like DEC's DCL)-in this case, your shell will obey the other operating system's wildcard rules. But even in this case, operating system designers stick to a reasonably similar set of wildcard rules.

  The fact that the shell defines wildcards, rather than the filesystem itself or the program you're running, has some important implications for a few commands. Most of the time, a program never sees wildcards. For example, typing:

      %

      lpr *

  is exactly the same as typing:

      %

      lpr



      file1 file2 file3 file4 file5

  In this case everything works as expected. But there are other situations in which wildcards don't work at all. Assume you want to read some files from a tape, which requires the command tar x ( 20.4 ) , so you type the command tar x *.txt . Will you be happy or disappointed?

  You'll be disappointed - unless older versions of the files you want are already in your current directory ( 1.21 ) . The shell expands the wildcard *.txt , according to what's in the current directory, before it hands the completed command line over to tar for execution . All tar gets is a list of files. But you're probably not interested in the current directory; you probably want the wildcard * to be expanded on the tape, retrieving any *.txt files that the tape has.

  There's a way to pass wildcards to programs, without having them interpreted by the shell. Simply put \*.txt in quotes ( 8.14 ) . The quotes prevent the UNIX shell from expanding the wildcard, passing it to the command unchanged. Programs that can be used in this way (like uucp and rcp ( 1.33 ) ) know how to handle wildcards, obeying the same rules as the shell (in fact, these programs usually start a shell to interpret their arguments). You only need to make sure that the programs see the wildcards, that they aren't stripped by the shell before it passes the command line to the program. As a more general rule, you should be aware of when and why a wildcard gets expanded, and you should know how to make sure that wildcards are expanded at an appropriate time.

  NOTE: If your shell understands the {} characters ( 9.5 ) , you can use them because they can generate any string - not just filenames that already exist. You have to type the unique part of each name, but you only have to type the common part once. For example, to extract the files called project/wk9/summary , project/wk14/summary , and project/wk15/summary from a tar tape, you might use:

      %

      tar xv project/wk{9,14,15}/summary


      x project/wk9/summary, 3161 bytes, 7 tape blocks
      x project/wk14/summary, 878 bytes, 2 tape blocks
      x project/wk15/summary, 2268 bytes, 5 tape blocks

  Some versions of tar understand wildcards, but many don't. There is a clever workaround ( 20.9 ) .

  Calculating Available Disk Space

  You can calculate your system’s free disk space with df -h (the -h produces more user- friendly output):
  $ df -h Filesystem /dev/disk0s2 devfs
   Size   Used  Avail Capacity  Mounted on
  465Gi  387Gi   77Gi    84%    /
  182Ki  182Ki    0Bi   100%    /dev
  $ df -H Filesystem /dev/disk0s2 devfs
  Size   Used  Avail Capacity  Mounted on
  499G   416G    83G    84%    /
  186k   186k     0B   100%    /dev
  0Bi    0Bi    0Bi   100%    /net
  0Bi    0Bi    0Bi   100%    /home
  map -hosts
  map auto_home
  localhost:/F_S7P7m8KJ6Yohz2Qm0HM2  465Gi  465Gi    0Bi   100%    /Volumes/...
  Here’s the breakdown for the output from the command:
  • The first column (Filesystem) shows the Unix device name for the volume.
  • The second column (Size) shows the total disk size, and it’s followed by the amount of disk space used up (Used) and the amount that’s available (Avail).
  • The Capacity column shows the percentage of disk space used. Many devices are shown at 100% because they’re not regular disks, but special Unix devices. All you really need to pay attention to is your main hard drive (mine is /dev/disk0s2).
  • The Mounted on column displays the paths for the volumes mounted on your com­ puter. The / is the root of your filesystem (a volume that is named Macintosh HD by default). /dev contains files that correspond to hardware devices, and /.vol ex­ poses some internals of the OS X filesystem called HFS+ file ID.
  Notice that I have one hard disk on my system, /dev/disk0s2 (which is 465 GB in size, of which 387 GB are used and 77 GB are still available).
  The df command has a second, more friendly output that uses the more common divide-by-10 rule for calculating sizes, rather than the more mathematically precise divide-by-2 rule of the -h flag:
  0B     0B     0B   100%    /net
  0B     0B     0B   100%    /home
  map -hosts
  map auto_home
  localhost:/F_S7P7m8KJ6Yohz2Qm0HM2   499G   499G     0B   100%    /Volumes/...
   62 | Chapter 3: Exploring the Filesystem
  These figures make more sense because I know that the hard disk mounted at /dev/ disk0s2 is actually 500 GB in size (though why it shows up as 499GB instead of 500GB is anyone’s guess!). You might prefer the more accurate -h output, but many people prefer -H since disk sizes are shown consistent with expectations.
  Yet another way to look at the data is to use the -m flag to have df show you 1 MB blocks, which rounds down all the tiny OS partitions like devfs and .vol to zero:
  $ df -m
  Filesystem 1M-blocks Used Available Capacity Mounted on /dev/disk0s2 476120 396514 79355 84% /
  devfs
  map -hosts
  map auto_home
  localhost:/F_S7P7m8KJ6Yohz2Qm0HM2    476120 476120
  Finally, in addition to raw disk space, another factor to keep track of with your OS X system is the number of inodes available. Inodes are the fundamental disk blocks that are grafted together to make space for all the different-sized files in your filesystem. A given disk in Unix has a finite number of files and directories that can be created, and even if there’s additional disk space available, running out of inodes effectively stops the disk from being used. This unusual event can happen if you have lots and lots (I’m talking millions and millions) of tiny files.
  The -i flag to df shows how you’re doing with inodes, providing details on how many inodes are allocated and available on each filesystem.
  Generally disks have plenty of unused inodes, so there’s nothing to worry about. For example, as you can see here, disk 0s2 has 20,315,203 available inodes:
  $ df -i
  Filesystem 512-blocks Used Available Capacity iused ifree %iused ... /dev/disk0s2 975093952 812060328 162521624 84% 101571539 20315203 83% ...
  devfs              363       363      0      100%       629
  0  100%  ...
  0  100%  ...
  0  100%  ...

  pwd
  cd
  "Print Working Directory". Shows the current location in the directory tree.
  cd
  cd, chdir
  "Change Directory". When typed all by itself, it returns you to your home directory.
  cd directory
  cd directory
  Change into the specified directory name. Example: cd /usr/src/linux
  cd ~
  "~" is an alias for your home directory. It can be used as a shortcut to your "home", or other directories relative to your home.
  cd ..
  cd..
  Move up one directory. For example, if you are in /home/vic and you type "cd ..", you will end up in /home.
  cd -
  Return to previous directory. An easy way to get back to your previous location!
  ls
  dir /w
  List all files in the current directory, in column format.
  ls directory
  dir directory
  List the files in the specified directory. Example:ls /var/log
  ls -l
  dir
  List files in "long" format, one file per line. This also shows you additional info about the file, such as ownership, permissions, date, and size.
  ls -a
  dir /a
  List all files, including "hidden" files. Hidden files are those files that begin with a ".", e.g. The .bash_history file in your home directory.
  ls -ld
  directory
  A "long" list of "directory", but instead of showing the directory contents, show the directory's detailed information. For example, compare the output of the following two commands:
  ls -l /usr/bin
  ls -ld /usr/bin
  ls /usr/bin/d*
  dir d*.*
  List all files whose names begin with the letter "d" in the /usr/bin directory.

### VO 300w
  ( download rails src)

  See: https://developer.apple.com/library/mac/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html

  $ man hier

  pwd
  "Print Working Directory". Shows the current location in the directory tree.

  cd
  Changes the working directory to your home directory.

  cd cd -
  Changes the working directory to the previous working directory.

  cd ~username
  Changes the working directory to the home directory of username. For example, cd ~bob changes the directory to the home directory of user bob.

  An absolute pathname begins with the root directory
  a relative pathname starts from the working directory
  ./
  ../

  cd directory
  Change into the specified directory name. Example: cd /usr/src/linux

  cd ..
  Move up one directory. For example, if you are in /home/vic and you type "cd ..", you will end up in /home.

  ls List all files in the current directory, in column format.

  ls directory
  List the files in the specified directory. Example:ls /var/log

  ls -l
  List files in "long" format, one file per line.

  ls -a

  List all files, including "hidden" files. Hidden files are those files that begin with a ".", e.g. The .bash_history file in your home directory.

  ls -ld directory

  A "long" list of "directory", but instead of showing the directory contents, show the directory's detailed information. For example, compare the output of the following two commands:

  ls -l /usr/bin
  ls -ld /usr/bin

  ls -lR recursive

  *tree

  -a     All files are printed.
  -d     List directories only.
  -f     Prints the full path prefix for each file.
  -x     Stay on the current file-system only.  Ala find -xdev.
  -L level Max display depth of the directory tree.
  -P pattern
  List only those files that match the wild-card pattern.
  -I pattern
  Do not list those files that match the wild-card pattern.
  -r     Sort the output in reverse alphabetic order.
  -t     Sort the output by last modification time instead of alphabetically.

  *du/df

  You can find the size of a file with the du (disk usage) command:

  $ du Documents/Outline.doc
  300     Documents/Outline.doc

  The size is reported in kilobytes, so Outline.doc is 300 KB in size.

  If you give du the name of a directory, it calculates the sizes of everything inside that directory, including any subdirectories and their contents:

## Wildcards 4m
  *

      Match zero or more characters. For example, a* matches the files a , ab , abc , abc.d , and so on.
  ?

      Match exactly one character. For example, a? matches aa , ab , ac , etc.
  [12..a..z]

      Match any character listed in the brackets. For example, a[ab] matches aa or ab .
  [a-z]

      Match all characters between a and z. For example, a[0-9] matches a0 , a1 , and so on, up to a9 .
  [!ab..z]

      Match any character that does not appear within the brackets. For example, a[!0-9] doesn't match a0 , but does match aa . bash , Korn, and newer Bourne shells only.
  [^ab..z]

      Match any character that does not appear within the brackets. For example, a[^0-9] doesn't match a0 , but does match aa . tcsh only.
      
  {word1,word2...}

      Match word1 , word2 , etc. E.g., a_{dog,cat,horse} matches the filenames a_dog , a_cat , and a_horse . bash and C shells only. These ( 9.5 ) actually aren't filename-matching wildcards. They expand any string, including filenames that don't exist yet, email addresses, and more.
  ?(abc)

      Match zero or one instance of abc . For example, x?(abc)x matches xx or xabcx . Korn shell only.
  *(abc)

      Match zero or more instances of abc . For example, x*(abc)x matches xx , xabcx , xabcabcx , etc. Korn shell only.
  +(abc)

      Match one or more instances of abc . For example, x+(abc)x matches xabcx , xabcabcx , etc. Korn shell only.
  !(abc)

      Match anything that doesn't contain abc . For example, x!(abc)x doesn't match xabcx or xabcabcx , but does match practically anything else that begins or ends with x . Korn shell only.
  ^ pat

      Match any name that doesn't match pat . pat must include at least one of the wildcards * , ? and [] . To match all except a single name, here's a trick: put brackets around one character. For instance, you can match all except abc with ^ab[c] . tcsh only. (For other shells, see nom ( 15.9 ) .)

  Note: wildcards do not match files whose names begin with a dot ( . ), like .cshrc . [1] This prevents you from deleting (or otherwise mucking around with) these files by accident. To match those files, type the dot literally. For example, .[a-z]* matches anything whose name starts with a dot and a lowercase letter. Watch out for plain .* , though; it matches the directory entries . and .. (see article 15.5 for suggestions on solving that problem).

      [1] Setting the bash variable glob_dot_filenames includes these names in wildcard expansion.

  And a final note: many operating systems (VAX/VMS and DOS included) consider a file's name and extension to be different entities; therefore, you can't use a single wildcard to match both. What do I mean? Consider the file abc.def . Under DOS or VMS, to match this filename you'd need the wildcard expression *.* . The first * matches the name (the part before the period), and the second matches the extension (the part after the period). Although UNIX uses extensions, they aren't considered a separate part of the filename, so a single * will match the entire name.

### VO 600w
  abbreviate filenames or refer to groups of files.

  Like a wildcard in a poker game, a wildcard in a filename can have any value.

  ? matches any single character.

  For example, letter? letterA , letter1, filenames with a non-printing character as their last letter, like letter ^C.

  The * wildcard matches any character or group of zero or more characters.

  For example, \*.txt matches all files whose names end with .txt ,

  For example, you may want to list files whose names end with .txt , mail , or let: use a separate * with each filename ending:

  \*.txt \*mail \*let

  list all filenames that begin with digits, or all filenames that begin with uppercase letters.

  program.[0123456789]

  wildcard [ character-list ] matches any single character that appears in the list. The character list can be any group of ASCII characters;

  if they are consecutive (e.g., A-Z, a-z, 0-9, or 3-5, for that matter), you can use a hyphen as shorthand for the range. For example, [a-zA-Z] means any alphabetic character.

  Wildcards never match / , which is both the name of the filesystem root ( 1.19 ) and the character used to separate directory names in a path.

  Therefore, the equivalent of rm * does virtually nothing on most operating systems. Under UNIX, it is very dangerous: it means "delete all the files in the current directory, regardless of their name."

  If a file's name begins with . , you always have to type the . explicitly.

  For example, .*rc matches all files whose names begin with . and end with rc .

  *

      Match zero or more characters. For example, a* matches the files a , ab , abc , abc.d , and so on.
  ?

      Match exactly one character. For example, a? matches aa , ab , ac , etc.
  
  [12..a..z]

      Match any character listed in the brackets. For example, a[ab] matches aa or ab .
  
  [a-z]

      Match all characters between a and z. For example, a[0-9] matches a0 , a1 , and so on, up to a9 .
  
  [!ab..z]

      Match any character that does not appear within the brackets. For example, a[!0-9] doesn't match a0 , but does match aa . bash , Korn, and newer Bourne shells only.
  
  [^ab..z]

      Match any character that does not appear within the brackets. For example, a[^0-9] doesn't match a0 , but does match aa . tcsh only.
  
  {word1,word2...}

      Match word1 , word2 , etc. E.g., a_{dog,cat,horse} matches the filenames a_dog , a_cat , and a_horse . bash and C shells only. These ( 9.5 ) actually aren't filename-matching wildcards. They expand any string, including filenames that don't exist yet, email addresses, and more.
      
  ?(abc)

      Match zero or one instance of abc . For example, x?(abc)x matches xx or xabcx . Korn shell only.
  *(abc)

      Match zero or more instances of abc . For example, x*(abc)x matches xx , xabcx , xabcabcx , etc. Korn shell only.
  +(abc)

      Match one or more instances of abc . For example, x+(abc)x matches xabcx , xabcabcx , etc. Korn shell only.
  !(abc)

      Match anything that doesn't contain abc . For example, x!(abc)x doesn't match xabcx or xabcabcx , but does match practically anything else that begins or ends with x . Korn shell only.
  ^ pat

      Match any name that doesn't match pat . pat must include at least one of the wildcards * , ? and [] . To match all except a single name, here's a trick: put brackets around one character. For instance, you can match all except abc with ^ab[c] . tcsh only. (For other shells, see nom ( 15.9 ) .)

  Note: wildcards do not match files whose names begin with a dot ( . ), like .cshrc . [1] This prevents you from deleting (or otherwise mucking around with) these files by accident. To match those files, type the dot literally. For example, .[a-z]* matches anything whose name starts with a dot and a lowercase letter. Watch out for plain .* , though; it matches the directory entries . and .. (see article 15.5 for suggestions on solving that problem).

  Wildcards can be used at any point or points within a path. Remember, wildcards only match names that already exist.

  You can't use them to create new files ( 9.4 ) - though some shells have curly braces ( {} ) ( 9.5 , 15.3 ) for doing that.

  Most of the time, a program never sees wildcards. For example, typing:

  $ lpr *

  is exactly the same as typing:
  $ lpr file1 file2 file3 file4 file5

  you want to read some files from a tape, which requires the command tar x ( 20.4 ) , so you type the command tar x *.txt .

  The shell expands the wildcard \*.txt , according to what's in the current directory, before it hands the completed command line over to tar for execution.

  Problem: reference file archive not current directory.

  use {} to generate any string - not just filenames that already exist. You have to type the unique part of each name, but you only have to type the common part once.

  For example, to extract the files called project/wk9/summary , project/wk14/summary , and project/wk15/summary from a tar tape, you might use:

  $ tar xv project/wk{9,14,15}/summary
  x project/wk9/summary, 3161 bytes, 7 tape blocks
  x project/wk14/summary, 878 bytes, 2 tape blocks
  x project/wk15/summary, 2268 bytes, 5 tape blocks

  put \*.txt in quotes to prevent the shell from expanding the wildcard

## File display 2m
  git clone RAILS

  cat README

  less README
  * scroll
  * search

  less \*.rb

  head -n 1

  (rails project)
  tail -n 1
  tail -f log/development.log
  tail -f /var/log/messages
  tail -f log/development.log /var/log/messages

  Calculating File Size and Disk Space

  You can find the size of a file with the du (disk usage) command: $ du Documents/Outline.doc
      300     Documents/Outline.doc
  The size is reported in kilobytes, so Outline.doc is 300 KB in size.
  If you give du the name of a directory, it calculates the sizes of everything inside that
  directory, including any subdirectories and their contents:
  $ du Library
  136 Library/Accounts
  64 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/MacOS
  8 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/Resources/bg.lproj 8 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/Resources/da.lproj 8 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/Resources/de.lproj 16 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/Resources/en.lproj ...
   Calculating File Size and Disk Space | 59
   This means that it’s not a great idea to type du /, unless you want to see a lot of information stream past your screen at a lightning pace!
  If you want the total for the directory, use -s (summarize):

  $ du -s Library
      41075320  Library
  If you’d like separate totals for all directories and files, including hidden ones, use a wildcard pattern that ignores the current (.) and parent (..) directories, as discussed earlier in this chapter:


  $ du -s * .[^.]* 86696 Desktop 73427240 Documents 13330568 Downloads 5508072 Dropbox 269120 Google Drive 41078120 Library
      ...
      8   .nchsoftware
      8   .profile
      8   .ssh
      64  .subversion
      48  .viminfo
      8   .vuescanrc
  To gain information about the size of the standard user applications in OS X, use the pattern /Applications/*.app:
  $ du -s /Applications/*.app
  1784120 /Applications/Aperture.app 3760 /Applications/App Store.app 20872 /Applications/Automator.app 8880 /Applications/Calculator.app 52832 /Applications/Calendar.app 11888 /Applications/Chess.app
  23296 /Applications/Contacts.app
  ...
  17864 /Applications/TextEdit.app
  656
  /Applications/Time Machine.app 1169280 /Applications/VMware Fusion.app 37952 /Applications/VueScan.app 3574832 /Applications/Xcode.app
  855160 /Applications/iMovie.app 382416 /Applications/iPhoto.app 153200 /Applications/iTunes.app
   60 | Chapter 3: Exploring the Filesystem
  Notice that the output is in alphabetical order, but all the uppercase filenames are sorted before the lowercase filenames (that is, TextEdit appears before iMovie in a case- sensitive sort).
  One option that’s worth keeping in mind when using du -s is -h, which produces more human-readable output:

  $ du -sh /Library/*
  3.1G /Library/Application Support 1001M /Library/Audio
       24M   /Library/Automator
      1.6M   /Library/Caches
        0B   /Library/ColorPickers
       92K   /Library/ColorSync
        0B   /Library/Components
        0B   /Library/Compositions
      512K   /Library/Contextual Menu Items
      127M   /Library/Desktop Pictures
      ...
        0B   /Library/Speech
        0B   /Library/Spelling
      1.9M   /Library/Spotlight
        0B   /Library/StartupItems
        0B   /Library/SystemProfiler
      668K   /Library/Updates
       21M   /Library/User Pictures
        0B   /Library/Video
      3.3M   /Library/WebServer
      8.5M   /Library/Widgets
       16K   /Library/iTunes



  While this is a bit more readable, the enormous /Library/Application Support, at 3.1 GB, doesn’t jump out as it would if the -h flag weren’t used and the output of 6507128 blocks were shown instead. It’s probably best to include the -h flag, but remember to scan the suffix letters to see if anything jumps out as being ridiculously large.


  You can also sort the largest directories to the top of the results with a command sequence like du -s /Library/* | sort -rn, or, better, only view the top 10 results with du -s /Library/* | sort -rn | head. I’ll explain com­ mand pipes and the tremendously useful sort command a bit later.

  Launching GUI Applications

  One great feature of OS X’s Unix command line is that you can interact with the graphical applications in Aqua. For example:
  • Drag a file or folder from the Finder onto a Terminal window and watch as its full pathname gets dropped in after the command prompt.
  • Want to use vi to edit a text file that’s on your Desktop? Just type vi on the command line, followed by a space, and then drag the file onto the Terminal window.
  • When viewing a file in the Finder, you’ll see what’s known as a proxy icon in the Finder’s title bar that shows you what directory you’re in. Type cd followed by a space, then drag the proxy icon into the Terminal window and hit Return; you’ll be taken to that same exact location, just in the Terminal.
  If you can have the Finder interact with the Terminal, it should be no surprise to you that you can also have the Terminal interact with other graphical applications on the Mac. For this, OS X offers the open command.
   164 | Chapter 7: Multitasking
  open
  By default, the open command works identically to double-clicking an icon in the Finder. To open up a picture file in your default picture editor, use:
  $ open peanut.jpg $
  If you don’t have a graphics-editing application like Photoshop installed, the image opens in Preview (/Applications). If Preview is already running, the peanut.jpg image file opens in a new window.
  The open command also lets you work at the command line with file matching, since it accepts more than one filename at a time. For example, if you need to open up a bunch of Microsoft Word files in a directory, just use:
  $ open *.doc $
  You can, however, get things a bit confused, because sometimes the system doesn’t know what to do with certain files. For example, try issuing the following command:
  $ open .profile $
  The default application that’s used when there’s no specific binding is TextEdit, which works in this instance, but look what happens when you try to open something it can’t recognize:
  $ open .sample.swp
  No application knows how to open /Users/taylor/Desktop/.sample.swp.
  In this case, open just couldn’t figure out what to do with this temporary scratch file from the vi editor. That’s because open uses a file’s creator and/or type code to determine which application should be used to open a particular file. And since vi’s scratch files don’t have a creator or type code, the command gets confused and ends up doing nothing.
  What Are Creator and Type Codes?
  Unlike in other operating systems, whenever you create and save a file with an application on the Mac, the application you use assigns its creator and type codes to the file. These codes are four characters in length and can contain upper- and lowercase letters, numbers, and even spaces. OS X uses these codes to figure out which icon gets assigned to certain files and, more importantly, to determine the default application for opening that file.
  For example, in the Terminal, you can create a blank file on your Desktop with the fol­ lowing command:
  $ touch ~/Desktop/myFile.txt
      Launching GUI Applications | 165
  As you can see from the file extension (.txt), this is a plain-text file. If you were to double- click on this file, and if you didn’t have another graphical text editor on your system, the file would open in TextEdit.
  However, if you rename that file and give it a .doc extension: $ mv myFile.txt myFile.doc
  you can trick the system into thinking that it’s a Word file. Don’t believe me? Just try double-clicking the file and see which application opens it!
  If you’ve installed the Xcode Tools on your Mac (https://developer.apple.com/technologies/ tools/), you can use a couple of special command-line utilities to peek inside a file to see its creator and type codes. For example, the following displays the output of the GetFi­ leInfo command (located in /usr/bin) when used on a Word file:
  $ GetFileInfo lmut_ch07.doc
  file: "/Users/taylor/Documents/Linux Journal/Column.42.docx" type: "WXBN"
  creator: "MSWD"
  attributes: avbstclinmedz
  created: 03/02/2009 20:45:22
  modified: 03/02/2009 20:45:22
  $
  Here you can see that the creator code is MSWD, short for Microsoft Word. Useful Starting Options for Use with open
  The open command has a lot of power accessible through command options. For ex­ ample, if you want to stream a bunch of input into a text file then open it in an Aqua file, you can do so by using the -f option:
  $ mdfind NIKON | open -f $
  This quick call to Spotlight generates a list of all filenames that reference or include NIKON. It would be easy to generate a printout with TextEdit, too.
  The most useful option for use with open is -a, which is used to specify an application to open. For example, you can launch Messages with the generic open command, but you need to know where it’s located on your system:
  $ open messages
  The file /Users/taylor/Desktop/messages does not exist.
  Add the -a option, though, and open knows that you’re talking about an application, so it’ll search in the /Applications directory to find and launch it:
  $ open -a messages
      166 | Chapter 7: Multitasking
  Notice that open is smart enough to ignore case: the actual application is called Messages. You can also use the open -a command to open applications that are in a subdirectory of /Applications. Want to launch the Console (located in /Applications/Utilities)? Use open -a console. Ready to compare the output of Activity Monitor to the ps command, as discussed earlier in this chapter? Launch Activity Monitor with open -a "activity monitor".
  If you want to open a file with TextEdit, there’s another option to open that’s worth knowing: use open -e, and whatever you specify will be opened with the TextEdit pro­ gram, regardless of its type. For example, if you wanted to open an HTML file in TextEdit instead of with BBEdit, you could use the following:
  $ open -e ~/Sites/someFile.html
  The open command will then look in your Sites folder for the file someFile.html and open
  it in TextEdit.
  Making open More Useful
  open makes it a breeze to launch your favorite applications, but because it requires that you type in the full application name, a few aliases are in order:
      alias word="open -a Microsoft\ Word"
      alias excel="open -a Microsoft\ Excel"
      alias gc="open -a GraphicConverter"
  With these added to your .profile, you can easily launch Graphic Converter by just en­ tering gc, and launch Microsoft Excel with excel.
  A more sophisticated approach would be to use a shell script wrapper that would give its arguments to open and, if they failed, try to figure out what application you were talking about. It’s an advanced topic, but here’s how that script might look:
  #!/bin/sh
      # open2 - a smart wrapper for the cool OS X 'open' command
      #   to make it even more useful. By default, open launches the
      #   appropriate application for a specified file or directory
      #   based on the Aqua bindings, and has a limited ability to
      #   launch applications if they're in the /Applications dir.
      # first off, whatever argument we're given, try it directly:
      open=/usr/bin/open
      if ! $open "$@" >/dev/null 2>&1 ; then
        if ! $open -a "$@" >/dev/null 2>&1 ; then
          # More than one arg?  Don't know how to deal with it: quit
          if [ $# -gt 1 ] ; then
            echo "open: Can't figure out how to open or launch $@" >&2
   Launching GUI Applications
  | 167
  exit 1 else
            case $(echo $1 | tr '[:upper:]' '[:lower:]') in
              acrobat      ) app="Acrobat Reader"             ;;
              address*     ) app="Contacts"                   ;;
              chat         ) app="Messages"                   ;;
              cpu          ) app="Activity Monitor"           ;;
              dvd          ) app="DVD Player"                 ;;
              word         ) app="Microsoft Word"             ;;
              excel        ) app="Microsoft Excel"            ;;
              prefs        ) app="System Preferences"         ;;
              qt|quicktime ) app="QuickTime Player"           ;;
              * ) echo "open: Don't know what to do with $1" >&2
  exit 1 esac
            echo "You asked for $1 but I think you mean $app." >&2
            $open -a "$app"
          fi
  fi fi
  exit 0
  This script has a simple table of nicknames for common applications, allowing you to type open2 qt to launch QuickTime Player, for example.
  This script is based on one in my book, Wicked Cool Shell Scripts (No Starch Press), which explains 101 powerful and interesting shell scripts. You can learn about the book, and download the above script for your­ self, at http://www.intuitive.com/wicked/.

### VO 300w
  less README
  * scroll
  * search

  less \*.rb

  head -n 1

  (rails project)
  tail -n 1
  tail -f log/development.log
  tail -f /var/log/messages
  tail -f log/development.log /var/log/messages

  *open

  • Drag a file or folder from the Finder onto a Terminal window and watch as its full pathname gets dropped in after the command prompt.

  • When viewing a file in the Finder, you’ll see what’s known as a proxy icon in the Finder’s title bar that shows you what directory you’re in. Type cd followed by a space, then drag the proxy icon into the Terminal window and hit Return; you’ll be taken to that same exact location, just in the Terminal.

  $ open *.doc

  $ open .profile

  The default application that’s used when there’s no specific binding is TextEdit,

  $ open .sample.swp

  No application knows how to open /Users/taylor/Desktop/.sample.swp.

  in the Terminal, you can create a blank file on your Desktop

  $ touch ~/Desktop/myFile.txt

  the file would open in TextEdit. However, if you rename that file and give it a .doc extension:

  $ mv myFile.txt myFile.doc

  you can trick the system into thinking that it’s a Word file.

  The open command has a lot of power accessible through command options. For ex­ ample, if you want to stream a bunch of input into a text file then open it in an Aqua file, you can do so by using the -f option:

  $ mdfind NIKON | open -f

  This quick call to Spotlight generates a list of all filenames that reference or include NIKON. It would be easy to generate a printout with TextEdit, too.

  The most useful option for use with open is -a, which is used to specify an application to open.

  search in the /Applications directory to find and launch it:

  $ open -a messages

  Notice that open is smart enough to ignore case:

  You can also use the open -a command to open applications that are in a subdirectory of /Applications.

  $ open -a console.

  open -a 'activity monitor'

  use open -e, and whatever you specify will be opened with the TextEdit program, regardless of its type.

  $ open -e ~/Sites/someFile.html

  a few aliases are in order:

  alias word="open -a Microsoft\ Word"

## File search 4m

  15.7 Getting a List of Matching Files with grep -l

  Normally when you run grep ( 27.1 ) on a group of files, the output lists the filename along with the line containing the search pattern. Sometimes you want to know only the names of the files, and you don't care to know the line (or lines) that match. In this case, use the -l (lowercase letter "l") option to list only filenames where matches occur. For example, the command:

      %

      grep -l R5



      file1 file2 ...



      > r5.filelist

  searches the files for a line containing the string R5 , produces a list of those filenames, and stores the list in r5.filelist . (This list might represent the files containing Release 5 documentation of a particular product.) Because these Release 5 files can now be referenced by one list, you can treat them as a single entity and run various commands on them all at once:

  `...`

  %

  print `cat r5.filelist`

  Print only the Release 5 files

  %

  grep UNIX `cat r5.filelist`


  Search limited to the Release 5 files

  You don't have to create a file list, though. You can insert the output of a grep directly into a command line with command substitution. For example, to edit only the subset of files containing R5 , you would type:

      %

      vi `grep -l R5

      files

      `

  grep -l is also good for shell programs that need to check whether a file contains a particular string. The traditional way to do that test is by throwing away grep 's output and checking its exit status:

      if grep

      something somefile

       >/dev/null
      then ...

  If somefile is huge, though, grep has to search all of it. Adding the grep -l option saves time because grep can stop searching after it finds the first matching line.

  15.8 Getting a List of Non-Matching Files with grep -c

  You can use the grep ( 27.2 ) option -c to tell you how many occurrences of a pattern appear in a given file, so you can also use it to find files that don't contain a pattern (i.e., zero occurrences of the pattern). Let's say you're indexing a troff ( 43.13 ) document and you want to make a list of files that don't yet contain indexing macros. What you need to find are files with zero occurrences of the string .XX . The command:

      %

      grep -c "\.XX" chapter*

  might produce the following output:

      chapter1:10
      chapter2:27
      chapter3:19
      chapter4:0
      chapter5:39
         ...

  This is all well and good, but suppose you need to check index entries in hundreds of reference pages? Well, just filter grep 's output by piping it through another grep . The above command can be modified as follows:

      %

      grep -c "\.XX" chapter* | grep :0

  This results in the following output:

      chapter4:0

  Using sed ( 34.24 ) to truncate the :0 , you can save the output as a list of files. For example, here's a trick for creating a list of files that don't contain index macros:

      %

      grep -c "\.XX" * | sed -n s/:0//p > ../not_indexed.list

  The sed -n command prints only the lines that contain :0 ; it also strips the :0 from the output so that ../not_indexed.list contains a list of files, one per line. The .. pathname ( 1.21 ) puts the not_indexed.list file into the parent directory - this is one easy way to keep grep from searching that file, but may not be worth the bother.

  [To edit all files that need index macros added, you could type:

      %

      vi `grep -c "\.XX" * | sed -n s/:0//p`

  which is more obvious once you start using backquotes a lot. You can put this into a little script named vgrep with a couple of safety features added:

  "$@"

  #!/bin/sh
  case $# in
  0|1) echo "Usage: `basename $0` pattern file [files...]" 1>&2 ;;
  *)  pat="$1"; shift
      grep -c "$pat" "$@" | sed -n 's/:0$//p'
     ;;
  esac

  Then you can type, for example, vi `vgrep "\.XX" *` . -JP  ]

   15.2 Filename Wildcards in a Nutshell

  This section summarizes the wildcards that are used for filename expansion. The shells use the same basic wildcards, though csh , tcsh , ksh , and bash have some extensions. Unless otherwise noted, assume that wildcards are valid for all shells.

  *

      Match zero or more characters. For example, a* matches the files a , ab , abc , abc.d , and so on.
  ?

      Match exactly one character. For example, a? matches aa , ab , ac , etc.
  [12..a..z]

      Match any character listed in the brackets. For example, a[ab] matches aa or ab .
  [a-z]

      Match all characters between a and z. For example, a[0-9] matches a0 , a1 , and so on, up to a9 .
  [!ab..z]

      Match any character that does not appear within the brackets. For example, a[!0-9] doesn't match a0 , but does match aa . bash , Korn, and newer Bourne shells only.
  [^ab..z]

      Match any character that does not appear within the brackets. For example, a[^0-9] doesn't match a0 , but does match aa . tcsh only.
  {word1,word2...}

      Match word1 , word2 , etc. E.g., a_{dog,cat,horse} matches the filenames a_dog , a_cat , and a_horse . bash and C shells only. These ( 9.5 ) actually aren't filename-matching wildcards. They expand any string, including filenames that don't exist yet, email addresses, and more.
  ?(abc)

      Match zero or one instance of abc . For example, x?(abc)x matches xx or xabcx . Korn shell only.
  *(abc)

      Match zero or more instances of abc . For example, x*(abc)x matches xx , xabcx , xabcabcx , etc. Korn shell only.
  +(abc)

      Match one or more instances of abc . For example, x+(abc)x matches xabcx , xabcabcx , etc. Korn shell only.
  !(abc)

      Match anything that doesn't contain abc . For example, x!(abc)x doesn't match xabcx or xabcabcx , but does match practically anything else that begins or ends with x . Korn shell only.
  ^ pat

      Match any name that doesn't match pat . pat must include at least one of the wildcards * , ? and [] . To match all except a single name, here's a trick: put brackets around one character. For instance, you can match all except abc with ^ab[c] . tcsh only. (For other shells, see nom ( 15.9 ) .)

  Note: wildcards do not match files whose names begin with a dot ( . ), like .cshrc . [1] This prevents you from deleting (or otherwise mucking around with) these files by accident. To match those files, type the dot literally. For example, .[a-z]* matches anything whose name starts with a dot and a lowercase letter. Watch out for plain .* , though; it matches the directory entries . and .. (see article 15.5 for suggestions on solving that problem).

      [1] Setting the bash variable glob_dot_filenames includes these names in wildcard expansion.

  And a final note: many operating systems (VAX/VMS and DOS included) consider a file's name and extension to be different entities; therefore, you can't use a single wildcard to match both. What do I mean? Consider the file abc.def . Under DOS or VMS, to match this filename you'd need the wildcard expression *.* . The first * matches the name (the part before the period), and the second matches the extension (the part after the period). Although UNIX uses extensions, they aren't considered a separate part of the filename, so a single * will match the entire name.

   17.1 The find Command Is Great; The Problem Is Finding How to Use It

  find is one of UNIX's most useful and important utilities. It finds files that match a given set of parameters, ranging from the file's name to its modification date. In this chapter, we'll be looking at many of the things it can do. As an introduction, here's a quick summary of its features and operators:

      %

      find



      path operators

  where path is the directory in which find will begin to search and operators (or, in more customary jargon, options ) tell find which files you're interested in. The operators are:

  -name   filename

      Find files with the given filename . This is the most commonly used operator. filename may include wildcards ( 15.2 ) , but if it does, it must be quoted to prevent the shell from interpreting the wildcards. See article 17.4 .
  -perm   mode

      Find files with the given access mode ( 22.2 ) . You must give the access mode in octal ( 1.23 ) . See articles 17.10 and 17.15 .
  -type   c

      The files of the given type, specified by c . c is a one-digit code; for example, f for a plain file, b for a block special file, l for a symbolic link, etc. See article 17.13 .
  -user   name

      Find files belonging to user name . name may also be a user ID number ( 38.3 ) . See article 17.16 .
  -group   name

      Find files belonging to group name . name may also be a group ID number ( 38.3 ) . See article 17.16 .
  -size   n

      Find files that are n blocks long. A block equals 512 bytes. The notation + n says "find files that are over n  blocks long." The notation n c says "find files that are n  characters long." Can you guess what + n c means? See article 17.14 .
  -inum   n

      Find files with the inode number ( 1.22 ) n . See article 17.10 .
  -atime   n

      Find files that were accessed n days ago. + n means "find files that were accessed over n days ago" (i.e., not accessed in the last n days). - n means "find files that were accessed less than n days ago" (i.e., accessed in the last n days). See articles 17.5 and 17.7 .
  -mtime   n

      Similar to atime , except that it checks the time the file's contents were modified. See articles 17.5 and 17.7 .
  -ctime   n

      Similar to atime , except that it checks the time the inode ( 1.22 ) was last changed. "Changed" means that the file was modified or that one of its attributes (for example, its owner) was changed. See articles 17.5 and 17.7 .
  -newer   file

      Find files that have been modified more recently than the given file . See articles 17.8 and 17.9 .

  Of course, you often want to take some action on files that match several criteria. So we need some way to combine several operators:

  operator1   -a   operator2

      Find files that match both operator1 and operator2 . The -a isn't necessary; when two search parameters are juxtaposed, find assumes you want files that match both of them. See article 17.12 .
  operator1   -o   operator2

      Find files that match either operator1 or operator2 . See article 17.6 .
  !   operator

      Find all files that do not match the given operator . The ! performs a logical NOT operation. See article 17.6 .
  \(  expression  \)

      Logical precedence; in a complex expression, evaluate this part of the expression before the rest. See article 17.6 .

  Another group of operators tells find what action to take when it locates a file:

  -print

      Print the file's name on standard output. See articles 17.2 and 17.3 .
  -exec   command

      Execute command . To include the pathname of the file that's just been found in command , use the special symbol {} . command must end with a backslash followed by a semicolon ( \; ). For example:

          %

          find -name "*.o" -exec rm -f {} \;

      tells find to delete any files whose names end in .o . See article 17.10 .
  -ok   command

      Same as -exec , except that find prompts you for permission before executing command . This is a useful way to test find commands. See article 17.10 .

  A last word: find is one of the tools that vendors frequently fiddle with, adding (or deleting) a few operators that they like (or dislike). The operators listed above should be valid on virtually any system. If you check your system's manual page, you may find a few others.

   In general, most commands do not understand directory structures, and rely on the shell to expand wildcards ( 15.2 ) to directory names. That is, to delete all files whose names end with a .o in a group of directories, you could type:

  %

  rm *.o */*.o */*/*.o

  find . -print

   The first arguments to find are directory and file pathnames - in that example, a dot ( . ) is one name for the current directory ( 1.21 ) . The arguments after the pathnames always start with a minus sign ( - ) and tell find what to do once it finds a file. These are the search operators. In this case, the filename is printed. You can use the tilde ( ~ ) ( 14.11 ) supported by the C shell, as well as particular paths. For example:

   ls -l `find . -print`

    17.5 Searching for Old Files

  If you want to find a file that is seven days old, use the -mtime operator:

      %

      find . -mtime 7 -print

  An alternate way is to specify a range of times:

      %

      find . -mtime +6 -mtime -8 -print

  mtime is the last modified time of a file. If you want to look for files that have not been used, check the access time with the -atime argument. A command to list all files that have not been read in 30 days or more is:

      %

      find . -type f -atime +30 -print

  It is difficult to find directories that have not been accessed because the find command modifies the directory's access time.

  There is another time associated with each file, called the ctime , the inode ( 1.22 ) change time. Access it with the -ctime operator. The ctime will have a more recent value if the owner, group, permission, or number of links has changed, while the file itself does not. If you want to search for files with a specific number of links, use the -links operator.

  Article 16.5 has more information about these three times. Article 17.7 explains how find checks them.

  Self-directed: find out how to use the -exec option to execute commands

   There are many well-known benefits provided by grep to the user who doesn't remember what his or her files contain. Even users of non-UNIX systems who make fun of its obscure name wish they had a utility with its power to search through a set of files for an arbitrary text pattern, known as a regular expression ( 26.4 ) .

  The main function of grep is to look for strings matching a regular expression and print only the lines found. Use grep when you want to look at how a particular word is used in one or more files. For example, here's how to list the lines in the file ch04 that contain either run-time or run time :

  $

  grep "run[- ]time" ch04

  Finding Text That Doesn't Match

  find. | grep -v

  19.15 Confusing Shell Wildcards and Regular Expressions
  Problem
  Sometimes you see .* sometimes just *, and sometimes you see [a-z]* but it means something other than what you thought. You use regular expressions for grep and sed but not in some places in bash. You can’t keep it all straight.
  Solution
  Relax; take a deep breath. You’re probably confused because you’re learning so much (or just using it too infrequently to remember it). Practice makes perfect, so keep trying.
  The rules aren’t that hard to remember for bash itself. After all, regular expression syntax is only used with the =~ comparison operator in bash. All of the other expres- sions in bash use shell pattern matching.
  Discussion
  The pattern matching used by bash uses some of the same symbols as regular expres- sions, but with different meanings. But it is also the case that you often have calls in your shell scripts to commands that use regular expressions—commands like grep and sed.
  We asked Chet Ramey, the current keeper of the bash source and all-around bash guru, if it was really the case that the =~ was the only use of regular expressions in bash. He concurred. He also was kind enough to supply a list of the various parts of bash syntax that use shell pattern matching. We’ve covered most, but not all of these topics in various recipes in this book. We offer the list here for completeness.
  Shell pattern matching is performed by:
  • Filename globbing (pathname expansion)
  • == and != operators for [[
  • case statements
  • $GLOBIGNORE handling
  • $HISTIGNORE handling
  • ${parameter#[#]word}
  • ${parameter%[%]word}
  • ${parameter/pattern/string}
  • Several bindable readline commands (glob-expand-word, glob-complete-word, etc.)
   480 | Chapter 19: Tips and Traps: Common Goofs for Novices
  • complete -G and compgen -G
  • complete -X and compgen -X
  • The help built-in’s `pattern` argument
  Thanks, Chet!

  Shining a Light on Spotlight

  A key feature included in OS X since Mac OS X Tiger is Spotlight, which indexes and stores metadata for all of the files on your system. This means that if you’re looking for a file by name, you can use locate or find, but if you’re looking for all images taken with a Nikon camera, or all PDF files that are more than 10 pages long, then Spotlight and its command-line tools are for you.
  Spotlight builds what Apple calls a metadata database that has a lot of information about the files on the system, in addition to their filenames. Whenever you conduct a Spotlight search—either through the graphical interface or on the command line—this metadata is searched to reveal information about the files on your system and offer up results. The two Spotlight commands that are analogous to the regular Unix commands ls and find are logically called mdls and mdfind.
  Let’s start with the mdls command—you’re going to be quite impressed!
  What’s Metadata?
  If you’ve been using computers for even a short time, you’re used to certain data being associated with each file you create. The filename, file size, date of creation—that’s all file- related data that’s familiar to you. But many files have additional, supplemental information.
  For example, Microsoft Word records the name and address of the file creator; Adobe Photoshop remembers what version of Photoshop you last used to edit an image file; and even digital cameras write out additional information for each image saved, including the camera name, the date and time the shot was taken, and often the film speed and lens focal length, all in EXIF format. This supplemental information is what OS X refers to as metadata, and it’s at the heart of Spotlight.
  Listing Spotlight Metadata with mdls
  Some of the most interesting types of files to explore with mdls are the pictures you take with a digital camera. Here’s what the ls command has to say about the JPEG file Peanut.jpg:
  $ ls -l IMG_1912.JPG
  -rw------- 1 taylor staff 8600047 May 7 12:17 IMG_1912.JPG
  Not particularly useful in terms of what’s actually inside the file. By comparison, here’s what the mdls command reports:
  $ mdls IMG_1912.JPG kMDItemAcquisitionMake kMDItemAcquisitionModel kMDItemAperture
  = "Canon"
  = "Canon EOS 50D"
  = 7
   128 | Chapter 5: Finding Files and Information
  kMDItemAuthors
      "
  = (
  )
  kMDItemBitsPerSample
  kMDItemColorSpace
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2012-05-07 18:17:06 +0000
  kMDItemContentType
  kMDItemContentTypeTree
      "public.jpeg",
      "public.image",
      "public.data",
      "public.item",
      "public.content"
  )
  kMDItemCopyright
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemEXIFVersion
  kMDItemExposureMode
  kMDItemExposureProgram
  kMDItemExposureTimeSeconds
  kMDItemFlashOnOff
  kMDItemFNumber
  kMDItemFocalLength
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemHasAlphaChannel
  kMDItemISOSpeed
  kMDItemKind
  kMDItemLogicalSize
  kMDItemOrientation
  kMDItemPhysicalSize
  kMDItemPixelCount
  kMDItemPixelHeight
  kMDItemPixelWidth
  kMDItemProfileName
  = "public.jpeg"
  = (
  ="
  = 2012-05-07 18:17:06 +0000 = "IMG_1912.JPG"
  = "2.2.1"
  =0
  = 4
  = 0.005555555555555556
  = 0
  = 11
  = 110
  = 2012-05-07 18:17:06 +0000 = 2012-05-07 18:17:06 +0000 ="
  =0
  =0
  =0
  =0
  =0
  =0
  = "IMG_1912.JPG"
  = 8600047
  = 20
  = 501
  = 8600047
  = "
  = 0
  = 400
  = "JPEG document"
  = 8600047
  =1
  = 8601600
  = 15054336
  = 4752
  = 3168
  = "sRGB IEC61966-2.1"
  = 32
  = "RGB"
  = 2012-05-07 18:17:06 +0000
   Shining a Light on Spotlight
  | 129
  kMDItemRedEyeOnOff
  kMDItemResolutionHeightDPI
  kMDItemResolutionWidthDPI
  kMDItemWhiteBalance
  = 0 = 72 = 72 = 1
  Quite a bit more useful information, thanks to Spotlight and its smart file parsing mod­ ules! Note that mdls offers the following details:
  • The camera used (Canon EOS 50D), as noted by kMDItemAcquisitionModel
  • The dimensions of the image (3168 x 4752), as noted by the kMDItem-PixelWidth
  and kMDItemPixelHeight items, respectively
  • The resolution of the image (72 DPI), as noted by kMDItemResolutionHeightDPI
  and kMDItemResolutionWidthDPI
  • Various other digital photo data, including exposure time (kMDItemExposureTime
  Seconds), focal length of the lens (kMDItemFocalLength), etc. Here’s another example of mdls output, this time with a PDF file:
  $ mdls ADT\ Writers\ Guide.pdf kMDItemAlternateNames
      "ADT Writers Guide.pdf"
  )
  kMDItemAuthors
      "Dave Taylor"
  = (
  = (
  = 2010-03-11 23:36:28 +0000
  )
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2010-03-22 21:55:54 +0000
  kMDItemContentType             = "com.adobe.pdf"
  kMDItemContentTypeTree         = (
  "com.adobe.pdf",
  "public.data",
  "public.item",
  "public.composite-content",
  "public.content"
  )
  kMDItemCreator
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemEncodingApplications
  = "Pages"
  = 2011-08-11 23:32:26 +0000 = "ADT Writers Guide"
  =(
      "Mac OS X 10.6.2 Quartz PDFContext"
  )
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  = 2010-03-22 21:55:54 +0000 = 2010-03-11 23:36:28 +0000 ="
  = 16
  =0 =0 =1 =0
   130
  | Chapter 5: Finding Files and Information
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemKind
  kMDItemLogicalSize
  kMDItemNumberOfPages
  kMDItemPageHeight
  kMDItemPageWidth
  kMDItemPhysicalSize
  kMDItemSecurityMethod
  kMDItemTitle
  kMDItemVersion
  = 0
  = "ADT Writers Guide.pdf"
  = 212658
  = 20
  = 501
  = 212658
  ="
  = "Portable Document Format (PDF)" = 212658
  = 5
  = 792
  = 612
  = 212992
  = "None"
  = "ADT Writers Guide"
  = "1.4"
  On a PDF document, the information includes the number of pages (as noted with kMDItemNumberOfPages; this document has 5), the application used to encode the PDF (Mac OS X 10.6.2 Quartz PDFContext, as noted by kMDItemEncodingApplications), and the date and time that the PDF file was created (March 11, 2010 at 23:36:28, as noted by kMDItemFSCreationDate).
  Let’s peek at one more file type before we explore what you can actually do with the Spotlight data, shall we? This time, it’s an MP3 file from my iTunes library:
  $ mdls 06\ Elise\ affair.mp3 kMDItemAlbum kMDItemAudioBitRate kMDItemAudioChannelCount kMDItemAudioSampleRate kMDItemAudioTrackNumber kMDItemAuthors
      "Thievery Corporation"
  )
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2011-12-19 00:04:16 +0000
  kMDItemContentType             = "public.mp3"
  kMDItemContentTypeTree         = (
      "public.mp3",
      "public.audio",
      "public.audiovisual-content",
      "public.data",
      "public.item",
      "public.content"
  )
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemDurationSeconds
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  = 2011-08-12 01:24:05 +0000
  = "06 Elise affair_.mp3"
  = 280.9774
  = 2011-12-19 00:04:16 +0000
  = 2010-10-05 05:22:24 +0000
  = "
  = "Lebanese Blonde"
  = 160000
  = 2
  = 44100
  = 6 = (
  = 2010-10-05 05:22:24 +0000
   Shining a Light on Spotlight
  | 131
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemKind
  kMDItemLogicalSize
  kMDItemMediaTypes
  Sound )
  kMDItemMusicalGenre
  kMDItemPhysicalSize
  kMDItemRecordingYear
  kMDItemTitle
  kMDItemTotalBitRate
  = 64
  =0
  =0
  =0
  =0
  =0
  = "06 Elise affair_.mp3" = 5723052
  = 20
  = 501
  = 5723052
  = "
  = "MP3 audio"
  = 5723052
  = (
  = "Electronic"
  = 5726208
  = 1998
  = "Elise affair"
  = 160000
  Encoded in each audio file is the artist (kMDItemAuthors), album (kMDItemAlbum), song name (kMDItemTitle), genre (kMDItemMusicalGenre), length of track (kMDItemDura tionSeconds), and much more, all accessible thanks to Spotlight and mdls.
  Finding Files with mdfind
  Knowing that there’s so much valuable and interesting information available through Spotlight, how do you actually do something useful with it? The answer is by using the mdfind command. However, while find has weird syntax, mdfind’s is even weirder and more unfriendly.
  The mdfind command matches files in the filesystem that meet a specific criterion or set of criteria, specified as:
  "metadata_field_name == 'pattern'"
  For example, to find all photographs taken with a Nikon camera, you’d use the following:
  $ mdfind "kMDItemAcquisitionModel == 'NIKON*'" /Users/taylor/Library/Mail/V2/Mailboxes/Film.mbox/
          965F1F99-FAB0-4EFE-9635-E04F1D6A4D84/Data/2/9/2/
          Attachments/292738/2/DLO_0887.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0006.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0008.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0001.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0010.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0013.jpg
   132
  | Chapter 5: Finding Files and Information
  Want to constrain the search to a specific subdirectory? You might be tempted to specify this directly as you would in find, but that’s not how it’s done. Instead, you need to use a flag called -onlyin, followed by a directory name. To find all the songs in your Jazz collection, use:
  $ mdfind -onlyin ~/Music "kMDItemMusicalGenre == 'Jazz'"
  You can also specify that you want a specific word anywhere in the metadata info by
  specifying just that word:
  $ mdfind -onlyin ~ Jazz /Users/taylor/Library/Safari/ReadingListArchives/
          381D47A1-2B73-4D2D-A388-6CAE189C92B4/Page.webarchive
      /Users/taylor/Desktop/LearnUnixOSX/ch05.asc
      /Users/taylor/Library/Calendars/74F70952-82D1-4222-BD5A-D4F03A465D55.caldav/
          015FBACF-C1E6-42AF-A3B0-37328DBC10A9.calendar/Events/
          M2CD-3-1-F2BEC546-28D9-4671-8E3D-F1E5114615E8.ics
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          20 Harlem Strut (Bonus Track).mp3
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          19 Alice Blue Gown (Bonus Track).mp3
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          18 Maple Leaf Rag (Bonus Track).mp3
      ...
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/Ch04.doc
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/Ch01.doc
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/app-a.doc
      /Users/taylor/Documents/BlogWorld Expo/jazz-performances.doc
      /Users/taylor/Documents/Blog Backups/Nov-1-2007/art_dolls.txt
  This output is quite interesting because it matches not only files where the word "Jazz" is part of the Spotlight metadata (as in the iTunes files), but also files that have "Jazz" in their name (the BlogWorld Expo document jazz-performances.doc), and even a plain- text file where the word "Jazz" appears in the text itself (art_dolls.txt). Pretty nifty, eh?
  Making Spotlight Useful
  Before leaving Spotlight, and certainly before we give up and assume that it’s only useful on the command line, let’s have a look at a couple of simple Unix commands that can extract useful information from the mdls information stream.
  Curious about the size in pixels of your JPEG files? You can quickly ascertain their height and width by using grep:
  $ mdls IMG_1912.JPG | grep -E '(PixelHeight|PixelWidth)' kMDItemPixelHeight = 4752
  kMDItemPixelWidth = 3168
  You can identify the duration of an audio file without loading it into iTunes or any other audio player by using:
   Shining a Light on Spotlight | 133
  $ mdls "06 Elise affair.mp3" | grep Duration kMDItemDurationSeconds = 280.9774
  You can also use find and xargs to identify files by name and then extract specific char­ acteristics:
  $ find . -name "*jpg" -print0 | xargs -0 mdls | grep FocalLength
  Or, you can actually use mdfind in the same manner (it does have a -0 option that makes
  it possible to match filenames that have spaces without things breaking):
  $ mdfind -0 "kMDItemFocalLength == '35'" | xargs -0 mdls | grep -E '(PixelHeight|PixelWidth|DisplayName)'
  kMDItemDisplayName
  kMDItemPixelHeight
  kMDItemPixelWidth
  kMDItemDisplayName
  kMDItemPixelHeight
  kMDItemPixelWidth
  = "Little-Hand.jpg"
  = 532
  = 800
  = "Peanut.jpg"
  = 531 = 800
  This last search matches all pictures on the entire system with a focal length of 35 (meaning, they were taken with a 35mm lens), and then displays the name, height, and width of each of the images it finds.
  These commands really beg for a simple shell script or two, where you could actually parse the output and reformat it as desired. We’ll talk about writing shell scripts a bit later in the book, but here’s a sneak preview of what such a script could do:
  $ photosize Peanut.jpg 800x531 at 300DPI
  The Spotlight commands accessible from the command line still haven’t been refined quite yet. You can get started with the information shown here, but don’t be surprised if a revision or two down the road turns the Spotlight commands into really powerful tools you can use for all sorts of tasks.

  Shining a Light on Spotlight
  A key feature included in OS X since Mac OS X Tiger is Spotlight, which indexes and stores metadata for all of the files on your system. This means that if you’re looking for a file by name, you can use locate or find, but if you’re looking for all images taken with a Nikon camera, or all PDF files that are more than 10 pages long, then Spotlight and its command-line tools are for you.
  Spotlight builds what Apple calls a metadata database that has a lot of information about the files on the system, in addition to their filenames. Whenever you conduct a Spotlight search—either through the graphical interface or on the command line—this metadata is searched to reveal information about the files on your system and offer up results. The two Spotlight commands that are analogous to the regular Unix commands ls and find are logically called mdls and mdfind.
  Let’s start with the mdls command—you’re going to be quite impressed!
  What’s Metadata?
  If you’ve been using computers for even a short time, you’re used to certain data being associated with each file you create. The filename, file size, date of creation—that’s all file- related data that’s familiar to you. But many files have additional, supplemental information.
  For example, Microsoft Word records the name and address of the file creator; Adobe Photoshop remembers what version of Photoshop you last used to edit an image file; and even digital cameras write out additional information for each image saved, including the camera name, the date and time the shot was taken, and often the film speed and lens focal length, all in EXIF format. This supplemental information is what OS X refers to as metadata, and it’s at the heart of Spotlight.
  Listing Spotlight Metadata with mdls
  Some of the most interesting types of files to explore with mdls are the pictures you take with a digital camera. Here’s what the ls command has to say about the JPEG file Peanut.jpg:
  $ ls -l IMG_1912.JPG
  -rw------- 1 taylor staff 8600047 May 7 12:17 IMG_1912.JPG
  Not particularly useful in terms of what’s actually inside the file. By comparison, here’s what the mdls command reports:
  $ mdls IMG_1912.JPG kMDItemAcquisitionMake kMDItemAcquisitionModel kMDItemAperture
  = "Canon"
  = "Canon EOS 50D"
  = 7
   128 | Chapter 5: Finding Files and Information
  kMDItemAuthors
      "
  = (
  )
  kMDItemBitsPerSample
  kMDItemColorSpace
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2012-05-07 18:17:06 +0000
  kMDItemContentType
  kMDItemContentTypeTree
      "public.jpeg",
      "public.image",
      "public.data",
      "public.item",
      "public.content"
  )
  kMDItemCopyright
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemEXIFVersion
  kMDItemExposureMode
  kMDItemExposureProgram
  kMDItemExposureTimeSeconds
  kMDItemFlashOnOff
  kMDItemFNumber
  kMDItemFocalLength
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemHasAlphaChannel
  kMDItemISOSpeed
  kMDItemKind
  kMDItemLogicalSize
  kMDItemOrientation
  kMDItemPhysicalSize
  kMDItemPixelCount
  kMDItemPixelHeight
  kMDItemPixelWidth
  kMDItemProfileName
  = "public.jpeg"
  = (
  ="
  = 2012-05-07 18:17:06 +0000 = "IMG_1912.JPG"
  = "2.2.1"
  =0
  = 4
  = 0.005555555555555556
  = 0
  = 11
  = 110
  = 2012-05-07 18:17:06 +0000 = 2012-05-07 18:17:06 +0000 ="
  =0
  =0
  =0
  =0
  =0
  =0
  = "IMG_1912.JPG"
  = 8600047
  = 20
  = 501
  = 8600047
  = "
  = 0
  = 400
  = "JPEG document"
  = 8600047
  =1
  = 8601600
  = 15054336
  = 4752
  = 3168
  = "sRGB IEC61966-2.1"
  = 32
  = "RGB"
  = 2012-05-07 18:17:06 +0000
   Shining a Light on Spotlight
  | 129
  kMDItemRedEyeOnOff
  kMDItemResolutionHeightDPI
  kMDItemResolutionWidthDPI
  kMDItemWhiteBalance
  = 0 = 72 = 72 = 1
  Quite a bit more useful information, thanks to Spotlight and its smart file parsing mod­ ules! Note that mdls offers the following details:
  • The camera used (Canon EOS 50D), as noted by kMDItemAcquisitionModel
  • The dimensions of the image (3168 x 4752), as noted by the kMDItem-PixelWidth
  and kMDItemPixelHeight items, respectively
  • The resolution of the image (72 DPI), as noted by kMDItemResolutionHeightDPI
  and kMDItemResolutionWidthDPI
  • Various other digital photo data, including exposure time (kMDItemExposureTime
  Seconds), focal length of the lens (kMDItemFocalLength), etc. Here’s another example of mdls output, this time with a PDF file:
  $ mdls ADT\ Writers\ Guide.pdf kMDItemAlternateNames
      "ADT Writers Guide.pdf"
  )
  kMDItemAuthors
      "Dave Taylor"
  = (
  = (
  = 2010-03-11 23:36:28 +0000
  )
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2010-03-22 21:55:54 +0000
  kMDItemContentType             = "com.adobe.pdf"
  kMDItemContentTypeTree         = (
  "com.adobe.pdf",
  "public.data",
  "public.item",
  "public.composite-content",
  "public.content"
  )
  kMDItemCreator
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemEncodingApplications
  = "Pages"
  = 2011-08-11 23:32:26 +0000 = "ADT Writers Guide"
  =(
      "Mac OS X 10.6.2 Quartz PDFContext"
  )
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  = 2010-03-22 21:55:54 +0000 = 2010-03-11 23:36:28 +0000 ="
  = 16
  =0 =0 =1 =0
   130
  | Chapter 5: Finding Files and Information
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemKind
  kMDItemLogicalSize
  kMDItemNumberOfPages
  kMDItemPageHeight
  kMDItemPageWidth
  kMDItemPhysicalSize
  kMDItemSecurityMethod
  kMDItemTitle
  kMDItemVersion
  = 0
  = "ADT Writers Guide.pdf"
  = 212658
  = 20
  = 501
  = 212658
  ="
  = "Portable Document Format (PDF)" = 212658
  = 5
  = 792
  = 612
  = 212992
  = "None"
  = "ADT Writers Guide"
  = "1.4"
  On a PDF document, the information includes the number of pages (as noted with kMDItemNumberOfPages; this document has 5), the application used to encode the PDF (Mac OS X 10.6.2 Quartz PDFContext, as noted by kMDItemEncodingApplications), and the date and time that the PDF file was created (March 11, 2010 at 23:36:28, as noted by kMDItemFSCreationDate).
  Let’s peek at one more file type before we explore what you can actually do with the Spotlight data, shall we? This time, it’s an MP3 file from my iTunes library:
  $ mdls 06\ Elise\ affair.mp3 kMDItemAlbum kMDItemAudioBitRate kMDItemAudioChannelCount kMDItemAudioSampleRate kMDItemAudioTrackNumber kMDItemAuthors
      "Thievery Corporation"
  )
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2011-12-19 00:04:16 +0000
  kMDItemContentType             = "public.mp3"
  kMDItemContentTypeTree         = (
      "public.mp3",
      "public.audio",
      "public.audiovisual-content",
      "public.data",
      "public.item",
      "public.content"
  )
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemDurationSeconds
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  = 2011-08-12 01:24:05 +0000
  = "06 Elise affair_.mp3"
  = 280.9774
  = 2011-12-19 00:04:16 +0000
  = 2010-10-05 05:22:24 +0000
  = "
  = "Lebanese Blonde"
  = 160000
  = 2
  = 44100
  = 6 = (
  = 2010-10-05 05:22:24 +0000
   Shining a Light on Spotlight
  | 131
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemKind
  kMDItemLogicalSize
  kMDItemMediaTypes
  Sound )
  kMDItemMusicalGenre
  kMDItemPhysicalSize
  kMDItemRecordingYear
  kMDItemTitle
  kMDItemTotalBitRate
  = 64
  =0
  =0
  =0
  =0
  =0
  = "06 Elise affair_.mp3" = 5723052
  = 20
  = 501
  = 5723052
  = "
  = "MP3 audio"
  = 5723052
  = (
  = "Electronic"
  = 5726208
  = 1998
  = "Elise affair"
  = 160000
  Encoded in each audio file is the artist (kMDItemAuthors), album (kMDItemAlbum), song name (kMDItemTitle), genre (kMDItemMusicalGenre), length of track (kMDItemDura tionSeconds), and much more, all accessible thanks to Spotlight and mdls.
  Finding Files with mdfind
  Knowing that there’s so much valuable and interesting information available through Spotlight, how do you actually do something useful with it? The answer is by using the mdfind command. However, while find has weird syntax, mdfind’s is even weirder and more unfriendly.
  The mdfind command matches files in the filesystem that meet a specific criterion or set of criteria, specified as:
  "metadata_field_name == 'pattern'"
  For example, to find all photographs taken with a Nikon camera, you’d use the following:
  $ mdfind "kMDItemAcquisitionModel == 'NIKON*'" /Users/taylor/Library/Mail/V2/Mailboxes/Film.mbox/
          965F1F99-FAB0-4EFE-9635-E04F1D6A4D84/Data/2/9/2/
          Attachments/292738/2/DLO_0887.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0006.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0008.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0001.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0010.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0013.jpg
   132
  | Chapter 5: Finding Files and Information
  Want to constrain the search to a specific subdirectory? You might be tempted to specify this directly as you would in find, but that’s not how it’s done. Instead, you need to use a flag called -onlyin, followed by a directory name. To find all the songs in your Jazz collection, use:
  $ mdfind -onlyin ~/Music "kMDItemMusicalGenre == 'Jazz'"
  You can also specify that you want a specific word anywhere in the metadata info by
  specifying just that word:
  $ mdfind -onlyin ~ Jazz /Users/taylor/Library/Safari/ReadingListArchives/
          381D47A1-2B73-4D2D-A388-6CAE189C92B4/Page.webarchive
      /Users/taylor/Desktop/LearnUnixOSX/ch05.asc
      /Users/taylor/Library/Calendars/74F70952-82D1-4222-BD5A-D4F03A465D55.caldav/
          015FBACF-C1E6-42AF-A3B0-37328DBC10A9.calendar/Events/
          M2CD-3-1-F2BEC546-28D9-4671-8E3D-F1E5114615E8.ics
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          20 Harlem Strut (Bonus Track).mp3
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          19 Alice Blue Gown (Bonus Track).mp3
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          18 Maple Leaf Rag (Bonus Track).mp3
      ...
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/Ch04.doc
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/Ch01.doc
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/app-a.doc
      /Users/taylor/Documents/BlogWorld Expo/jazz-performances.doc
      /Users/taylor/Documents/Blog Backups/Nov-1-2007/art_dolls.txt
  This output is quite interesting because it matches not only files where the word "Jazz" is part of the Spotlight metadata (as in the iTunes files), but also files that have "Jazz" in their name (the BlogWorld Expo document jazz-performances.doc), and even a plain- text file where the word "Jazz" appears in the text itself (art_dolls.txt). Pretty nifty, eh?
  Making Spotlight Useful
  Before leaving Spotlight, and certainly before we give up and assume that it’s only useful on the command line, let’s have a look at a couple of simple Unix commands that can extract useful information from the mdls information stream.
  Curious about the size in pixels of your JPEG files? You can quickly ascertain their height and width by using grep:
  $ mdls IMG_1912.JPG | grep -E '(PixelHeight|PixelWidth)' kMDItemPixelHeight = 4752
  kMDItemPixelWidth = 3168
  You can identify the duration of an audio file without loading it into iTunes or any other audio player by using:
   Shining a Light on Spotlight | 133
  $ mdls "06 Elise affair.mp3" | grep Duration kMDItemDurationSeconds = 280.9774
  You can also use find and xargs to identify files by name and then extract specific char­ acteristics:
  $ find . -name "*jpg" -print0 | xargs -0 mdls | grep FocalLength
  Or, you can actually use mdfind in the same manner (it does have a -0 option that makes
  it possible to match filenames that have spaces without things breaking):
  $ mdfind -0 "kMDItemFocalLength == '35'" | xargs -0 mdls | grep -E '(PixelHeight|PixelWidth|DisplayName)'
  kMDItemDisplayName
  kMDItemPixelHeight
  kMDItemPixelWidth
  kMDItemDisplayName
  kMDItemPixelHeight
  kMDItemPixelWidth
  = "Little-Hand.jpg"
  = 532
  = 800
  = "Peanut.jpg"
  = 531 = 800
  This last search matches all pictures on the entire system with a focal length of 35 (meaning, they were taken with a 35mm lens), and then displays the name, height, and width of each of the images it finds.
  These commands really beg for a simple shell script or two, where you could actually parse the output and reformat it as desired. We’ll talk about writing shell scripts a bit later in the book, but here’s a sneak preview of what such a script could do:
  $ photosize Peanut.jpg 800x531 at 300DPI
  The Spotlight commands accessible from the command line still haven’t been refined quite yet. You can get started with the information shown here, but don’t be surprised if a revision or two down the road turns the Spotlight commands into really powerful tools you can use for all sorts of tasks.

  9.1 Finding All Your MP3 Files Problem

  You have MP3 audio files scattered all over your filesystem. You’d like to move them all into a single location so that you can organize them and then copy them onto a music player.
   184
   Solution
  The find utility can locate all of those files and then execute a command to move them where you want. For example:
       $ find . -name '*.mp3' -print -exec mv '{}' ~/songs \;

  Discussion

  The syntax for the find utility is unlike other Unix tools. It doesn’t use options in the typical way, with dash and single-letter collections up front followed by several words of arguments. Rather, the options look like short words, and are ordered in a logical sequence describing the logic of which files are to be found, and what to do with them, if anything, when they are found. These word-like options are often called predicates.

  A find command’s first arguments are the directory or directories in which to search. A typical use is simply (.) for the current directory. But you can provide a whole list of directories, or even search the entire filesystem (permissions allowing) by specify- ing the root of the filesystem (/) as the starting point.

  In our example the first option (the -name predicate) specifies the pattern we will search for. Its syntax is like the bash pattern matching syntax, so *.mp3 will match all filenames that end in the characters ".mp3". Any file that matches this pattern is con- sidered to return true and will thus continue to the next predicate of the command.

  Think of it this way: find will climb around on the filesystem and each filename that it finds it will present to this gauntlet of conditions that must be run. Any condition that is true is passed. Encounter a false and that filename’s turn is immediately over, and the next filename is processed.

  Now the -print condition is easy. It is always true and it has the side effect of print- ing the name to standard output. So any file that has made it this far in the sequence of conditions will have its name printed.

  The -exec is a bit odd. Any filename making it this far will become part of a com- mand that is executed. The remainder of the lineup to the \; is the command to be executed. The {} is replaced by the name of the file that was found. So in our exam- ple, if find encounters a file named mhsr.mp3 in the ./music/jazz subdirectory, then the command that will be executed will be:
       mv ./music/jazz/mhsr.mp3 ~/songs
  The command will be issued for each file that matches the pattern. If lots and lots of matching files are found, lots and lots of commands will be issued. Sometimes this is too demanding of system resources and it can be a better idea to use find just to find the files and print the filenames into a datafile and issue fewer commands by
   Finding All Your MP3 Files | 185
  consolidating arguments several to a line. (But with machines getting faster all the time, this is less and less of an issue. It might even be something worthwhile for your dual core or quad core processor to do.)

  9.2 Handling Filenames Containing Odd Characters Problem
  You used a find command like the one in Recipe 9.1, "Finding All Your MP3 Files" but the results were not what you intended because many of your filenames contain odd characters.
  Solution
  First, understand that to Unix folks, odd means "anything not a lowercase letter, or maybe a number." So uppercase, spaces, punctuation, and character accents are all odd. But you’ll find all of those and more in the names of many songs and bands.
  Depending on the oddness of the characters, your system, tools, and goal, it might be enough to simply quote the replacement string (i.e., put single quotes around the {}, as in '{}') . You did test your command first, right?
  If that’s no good, try using the -print0 argument to find and the -0 argument to xargs. -print0 tells find to use the null character (\0) instead of whitespace as the output delimiter between pathnames found. -0 then tells xargs the input delimiter. These will always work, but they are not supported on every system.
  The xargs command takes whitespace delimited (except when using -0) pathnames from standard input and executes a specified command on as many of them as possi- ble (up to a bit less than the system’s ARG_MAX value; see Recipe 15.13, "Working Around "argument list too long" Errors"). Since there is a lot of overhead associated with calling other commands, using xargs can drastically speed up operations because you are calling the other command as few times as possible, rather than each time a pathname is found.
   186 | Chapter 9: Finding Files: find, locate, slocate
   So, to rewrite the solution from Recipe 9.1, "Finding All Your MP3 Files" to handle odd characters:
       $ find . -name '*.mp3' -print0 | xargs -i -0 mv '{}' ~/songs
  Here is a similar example demonstrating how to use xargs to work around spaces in a path or filename when locating and then coping files:
       $ locate P1100087.JPG PC220010.JPG PA310075.JPG PA310076.JPG | xargs -i cp '{}' .
  Discussion
  There are two problems with this approach. One is that not all versions of xargs sup- port the -i option, and the other is that the -i option eliminates argument grouping, thus negating the speed increase we were hoping for. The problem is that the mv command needs the destination directory as the final argument, but traditional xargs will simply take its input and tack it onto the end of the given command until it runs out of space or input. The results of that behavior applied to an mv command would be very, very ugly. So some versions of xargs provide a -i switch that defaults to using {} (like find), but using -i requires that the command be run one at a time. So the only benefit over using find’s -exec is the odd character handling.
  However, the xargs utility is most effective when used in conjunction with find and a command like chmod that just wants a list of arguments to process. You can really see a vast speed improvement when handling large numbers of pathnames. For example:
       $ find some_directory -type f -print0 | xargs -0 chmod 0644
  See Also
  • man find
  • man xargs
  • Recipe 9.1, "Finding All Your MP3 Files"
  • Recipe 15.13, "Working Around "argument list too long" Errors"
  9.3 Speeding Up Operations on Found Files Problem
  You used a find command like the one in Recipe 9.1, "Finding All Your MP3 Files" and the resulting operations take a long time because you found a lot of files, so you want to speed it up.
   Speeding Up Operations on Found Files | 187
   Solution
  See the discussion on xargs Recipe 9.2, "Handling Filenames Containing Odd Characters."
  See Also
  • Recipe 9.1, "Finding All Your MP3 Files"
  • Recipe 9.2, "Handling Filenames Containing Odd Characters"
  9.4 Finding Files Across Symbolic Links Problem
  You issued a find command to find your .mp3 files but it didn’t find all of them—it missed all those that were part of your filesystem but were mounted via a symbolic link. Is find unable to cross that kind of boundary?
  Solution
  Use the -follow predicate. The example we used before becomes:
  $ find . -follow -name '*.mp3' -print0 | xargs -i -0 mv '{}' ~/songs
  Discussion
  Sometimes you don’t want find to cross over onto other filesystems, which is where symbolic links originated. So the default for find is not to follow a symbolic link. If you do want it to do so, then use the -follow option as the first option in the list on your find command.
  See Also
  • man find
  9.5 Finding Files Irrespective of Case Problem
  Some of your MP3 files end with .MP3 rather than .mp3. How do you find those?
   188 | Chapter 9: Finding Files: find, locate, slocate
   Solution
  Use the -iname predicate (if your version of find supports it) to run a case-insensitive search, rather than just -name. For example:
       $ find . -follow -iname '*.mp3' -print0 | xargs -i -0 mv '{}' ~/songs
  Discussion
  Sometimes you care about the case of the filename and sometimes you don’t. Use the -iname option when you don’t care, in situations like this, where .mp3 or .MP3 both indicate that the file is probably an MP3 file. (We say probably because on Unix-like systems you can name a file anything that you want. It isn’t forced to have a particu- lar extension.)
  One of the most common places where you’ll see the upper- and lowercase issue is when dealing with Microsoft Windows-compatible filesystems, especially older or "lowest common denominator" filesystems. A digital camera that we use stores its files with filenames like PICT001.JPG, incrementing the number with each picture. If you were to try:
       $ find . -name '*.jpg' -print
  you wouldn’t find many pictures. In this case you could also try:
       $ find . -name '*.[Jj][Pp][Gg]' -print
  since that regular expression will match either letter in brackets, but that isn’t as easy to type, especially if the pattern that you want to match is much longer. In prac- tice, -iname is an easier choice. The catch is that not every version of find supports the -iname predicate. If your system doesn’t support it, you could try tricky regular expressions as shown above, use multiple -name options with the case variations you expect, or install the GNU version of find.
  See Also
  • man find
  9.6 Finding Files by Date Problem
  Suppose someone sent you a JPEG image file that you saved on your filesystem a few months ago. Now you don’t remember where you put it. How can you find it?
   Finding Files by Date | 189
   Solution
  Use a find command with the -mtime predicate, which checks the date of last modifi- cation. For example:
       find . -name '*.jpg' -mtime +90 -print
  Discussion
  The -mtime predicate takes an argument to specify the timeframe for the search. The 90 stands for 90 days. By using a plus sign on the number (+90) we indicate that we’re looking for a file modified more than 90 days ago. Write -90 (using a minus sign) for less than 90 days. Use neither a plus nor minus to mean exactly 90 days.
  There are several predicates for searching based on file modification times and each take a quantity argument. Using a plus, minus, or no sign indicates greater than, less than, or equals, respectively, for all of those predicates.
  The find utility also has logical AND, OR, and NOT constructs so if you know that the file was at least one week old (7 days) but not more than 14 days old, you can combine the predicates like this:
       $ find . -mtime +7 -a -mtime -14 -print
  YoucangetevenmorecomplicatedusingORaswellasANDandevenNOTto combine conditions, as in:
  $ find . -mtime +14 -name '*.text' -o \( -mtime -14 -name '*.txt' \) -print
  This will print out the names of files ending in .text that are older than 14 days, as
  well as those that are newer than 14 days but have .txt as their last 4 characters.
  You will likely need parentheses to get the precedence right. Two predicates in sequencearelikealogicalAND,whichbindstighterthananOR(infindasinmost languages). Use parentheses as much as you need to make it unambiguous.
  Parentheses have a special meaning to bash, so we need to escape that meaning, and write them as \( and \) or inside of single quotes as '(' and ')'. You cannot use sin- gle quotes around the entire expression though, as that will confuse the find com- mand. It wants each predicate as its own word.
  See Also
  • man find
   190 | Chapter 9: Finding Files: find, locate, slocate
   9.7 Finding Files by Type
  Problem
  You are looking for a directory with the word "java" in it. When you tried:
       $ find . -name '*java*' -print
  you got way too many files—including all the Java source files in your part of the filesystem.
  Solution
  Use the -type predicate to select only directories: $ find . -type d -name '*java*' -print
  Discussion
  We put the -type d first followed by the -name *java*. Either order would have found the same set of files. By putting the -type d first in the list of options, though, the search will be slightly more efficient: as each file is encountered, the test will be made to see if it is a directory and then only directories will have their names checked against the pattern. All files have names; relatively few are directories. So this ordering eliminates most files from further consideration before we ever do the string comparison. Is it a big deal? With processors getting faster all the time, it mat- ters less so. With disk sizes getting bigger all the time, it matters more so. There are several types of files for which you can check, not just directories. Table 9-1 lists the single characters used to find these types of files.
  Table 9-1. Characters used by find’s -type predicate
  Key Meaning
  b block special file
  c character special file
  d directory
  p pipe (or "fifo")
  f plain ol’ file
  l symbolic link
  s socket
  D (Solaris only) "door"
     Finding Files by Type
  | 191
   See Also
  • man find
  9.8 Finding Files by Size Problem
  You want to do a little housecleaning, and to get the most out of your effort you are going to start by finding your largest files and deciding if you need to keep them around. But how do you find your largest files?
  Solution
  Use the -size predicate in the find command to select files above, below, or exactly a certain size. For example:
       find . -size +3000k -print
  Discussion
  Like the numeric argument to -mtime, the -size predicate’s numeric argument can be preceded by a minus sign, plus sign, or no sign at all to indicate less than, greater than, or exactly equal to the numeric argument. So we’ve indicated, in our example, that we’re looking for files that are greater than the size indicated.
  The size indicated includes a unit of k for kilobytes. If you use c for the unit, that means just bytes (or characters). If you use b, or don’t put any unit, that indicates a size in blocks. (The block is a 512-byte block, historically a common unit in Unix systems.) So we’re looking for files that are greater than 3 MB in size.
  See Also
  • man find • man du
  9.9 Finding Files by Content Problem
  How do you find a file of some known content? Let’s say that you had written an important letter and saved it as a text file, putting .txt on the end of the filename. Beyond that, the only thing you remember about the content of the letter is that you had used the word "portend."
   192 | Chapter 9: Finding Files: find, locate, slocate
   Solution
  If you are in the vicinity of that file, say within the current directory, you can start with a simple grep:
       grep -i portend *.txt
  With the -i option, grep will ignore upper- and lowercase difference. This command may not be sufficient to find what you’re looking for, but start simply. Of course, if you think the file might be in one of your many subdirectories, you can try to reach all the files that are in subdirectories of the current directory with this command:
       grep -i portend */*.txt
  Let’s face it, though, that’s not a very thorough search.
  If that doesn’t do it, let’s use a more complete solution: the find command. Use the -exec option on find so that if the predicates are true up to that point, it will exe- cute a command for each file it finds. You can invoke grep or other utilities like this:
       find . -name '*.txt' -exec grep -Hi portend '{}' \;
  Discussion
  We use the -name '*.txt' construct to help narrow down the search. Any such test will help, since having to run a separate executable for each file that it finds is costly in time and CPU horsepower. Maybe you have a rough idea of how old the file is (e.g., -mdate -5 or some such).
  The '{}' is where the filename is put when executing the command. The \; indi- cates the end of the command, in case you want to continue with more predicates. Both the braces and the semicolon need to be escaped, so we quote one and use the backslash for the other. It doesn’t matter which way we escape them, only that we do escape them, so that bash doesn’t misinterpret them.
  On some systems, the -H option will print the name of the file if grep finds some- thing. Normally, with only one filename on the command, grep won’t bother to name the file, it just prints out the matching line that it finds. Since we’re searching through many files, we need to know which file was grepped.
  If you’re running a version of grep that doesn’t have the -H option, then just put /dev/ null as one of the filenames on the grep command. The grep command will then have more than one file to open, and will print out the filename if it finds the text.
  See Also
  • man find

   Finding Files by Content | 193
  9.10 Finding Existing Files and Content Fast Problem
  You’d like to be able to find files without having to wait for a long find command to complete, or you need to find a file with some specific content.
  Solution
  If your system has locate, slocate, Beagle, Spotlight or some other indexer, you are already set. If not, look into them.
  As we discussed in Recipe 1.3, "Finding and Running Commands", locate and slocate consult database files about the system (usually compiled and updated by a cron job) to find file or command names almost instantly. The location of the actual database files, what is indexed therein, and how often, may vary from system to sys- tem. Consult your system’s manpages for details.
       $ locate apropos
       /usr/bin/apropos
       /usr/share/man/de/man1/apropos.1.gz
       /usr/share/man/es/man1/apropos.1.gz
       /usr/share/man/it/man1/apropos.1.gz
       /usr/share/man/ja/man1/apropos.1.gz
       /usr/share/man/man1/apropos.1.gz
  locate and slocate don’t index content though, so see Recipe 9.9, "Finding Files by Content" for that.
  Beagle and Spotlight are examples of a fairly recent technology known as desktop search engines or indexers. Google Desktop Search and Copernic Desktop Search are two examples from the Microsoft Windows world. Desktop search tools use some kind of indexer to crawl, parse, and index the names and contents of all of the files (and usually email messages) in your personal file space; i.e., your home directory on a Unix or Linux system. This information is then almost instantly available to you when you look for it. These tools are usually very configurable, graphical, operate on a per-user basis, and index the contents of your files.
  Discussion
  slocate stores permission information (in addition to filenames and paths) so that it will not list programs to which the user does not have access. On most Linux sys- tems locate is a symbolic link to slocate; other systems may have separate programs, or may not have slocate at all. Both of these are command-line tools that crawl and index the entire filesystem, more or less, but they only contain filenames and locations.

  Find all .c files modified more recently than your Makefile.
  Shell...
  find . -name ' *.c' -newer Makefile -print


    GUI.....
  Open the Explorer, navigate to the correct directory, click on the Makefile, and note the modification time. Then bring up Tools/Find, and enter *.c for the file specification. Select the date tab, and enter the date you noted for the Makefile in the first date field. Then hit OK.

  Shell...
  zip archive.zip *.h *.c -or- tar cvf archive.tar *.h *.c
  GUI.....
  Bring up a ZIP utility (such as the shareware WinZip [URL41], select "Create New Archive," enter its name, select the source directory in the add dialog, set the filter to "* .c", click "Add," set the filter to "* .h", click "Add," then close the archive. ̈

  Shell...
  find . -name '*.java' -mtime +7 -print
  GUI.....
  Click and navigate to "Find files," click the "Named" field and type in "*.java", select the "Date Modified" tab. Then select "Between." Click on the starting date and type in the starting date of the beginning of the project. Click on the ending date and type in the date of a week ago today (be sure to have a calendar handy). Click on "Find Now."
  Shell...
  find . -name '*.java' -mtime +7 -print |
       xargs grep 'java.awt'
  GUI.....
  Load each file in the list from the previous example into an editor and search for the string "java.awt". Write down the name of each file containing a match.
   Construct a zip/tar archive of my source.
  Which Java files have not been changed in the last week?
  Of those files, which use the awt libraries?
  Clearly the list could go on. The shell commands may be obscure or terse, but they are powerful and concise. And, because shell commands can be combined into script files (or command files under Windows systems), you can build sequences of commands to automate things you do often.

  SEARCHING FOR FILES

  As we have wandered around our Linux system, one thing has become abundantly clear: A typical Linux system has a lot of files! This raises the question "How
  do we find things?" We already know that the Linux filesystem is well organized according to conventions that have been passed down from one generation of Unix-like systems to the next, but the sheer number of files can present a daunting problem.
  In this chapter, we will look at two tools that are used to find files on a system:
    locate—Find files by name.
    find—Search for files in a directory hierarchy.
  We will also look at a command that is often used with file-search com- mands to process the resulting list of files:
    xargs—Build and execute command lines from standard input.
  In addition, we will introduce a couple of commands to assist us in our explorations:
    touch—Change file times.
    stat—Display file or filesystem status.
  locate—Find Files the Easy Way
  The locate program performs a rapid database search of pathnames and then outputs every name that matches a given substring. Say, for example, we want to find all the programs with names that begin with zip. Since we are looking for programs, we can assume that the name of the directory containing the programs would end with bin/. Therefore, we could try to use locate this way to find our files:
  [me@linuxbox ~]$ locate bin/zip
  locate will search its database of pathnames and output any that contain
  the string bin/zip:
               /usr/bin/zip
               /usr/bin/zipcloak
               /usr/bin/zipgrep
               /usr/bin/zipinfo
               /usr/bin/zipnote
               /usr/bin/zipsplit
  If the search requirement is not so simple, locate can be combined with other tools, such as grep, to design more interesting searches:
  [me@linuxbox ~]$ locate zip | grep bin /bin/bunzip2
  /bin/bzip2
  /bin/bzip2recover
               /bin/gunzip
               /bin/gzip
               /usr/bin/funzip
               /usr/bin/gpg-zip
               /usr/bin/preunzip
               /usr/bin/prezip
               /usr/bin/prezip-bin
               /usr/bin/unzip
               /usr/bin/unzipsfx
               /usr/bin/zip
               /usr/bin/zipcloak
               /usr/bin/zipgrep
               /usr/bin/zipinfo
               /usr/bin/zipnote
               /usr/bin/zipsplit
  The locate program has been around for a number of years, and several different variants are in common use. The two most common ones found in modern Linux distributions are slocate and mlocate, though they are usually
        188
  Chapter 17
  accessed by a symbolic link named locate. The different versions of locate have overlapping options sets. Some versions include regular-expression matching (which we’ll cover in Chapter 19) and wildcard support. Check the man page for locate to determine which version of locate is installed.
      WHERE DOES THE LOCATE DATABASE COME FROM?
  You may notice that, on some distributions, locate fails to work just after the system is installed, but if you try again the next day, it works fine. What gives? The locate database is created by another program named updatedb. Usually, it is run periodically as a cron job; that is, a task performed at regular intervals by the cron daemon. Most systems equipped with locate run updatedb once a day. Since the database is not updated continuously, you will notice that very recent files do not show up when using locate. To overcome this, it’s possible to run the updatedb program manually by becoming the superuser and running updatedb
  at the prompt.
     find—Find Files the Hard Way
  While the locate program can find a file based solely on its name, the find program searches a given directory (and its subdirectories) for files based on a variety of attributes. We’re going to spend a lot of time with find because it has a bunch of interesting features that we will see again and again when we start to cover programming concepts in later chapters.
  In its simplest use, find is given one or more names of directories to search. For example, it can produce a list of our home directory:
  [me@linuxbox ~]$ find ~
  On most active user accounts, this will produce a large list. Since the
  list is sent to standard output, we can pipe the list into other programs. Let’s use wc to count the number of files:
  [me@linuxbox ~]$ find ~ | wc -l 47068
  Wow, we’ve been busy! The beauty of find is that it can be used to identify files that meet specific criteria. It does this through the (slightly strange) application of tests, actions, and options. We’ll look at the tests first.
  Tests
  Let’s say that we want a list of directories from our search. To do this, we could add the following test:
  [me@linuxbox ~]$ find ~ -type d | wc -l 1695
        Searching for Files 189
  Adding the test -type d limited the search to directories. Conversely, we could have limited the search to regular files with this test:
  [me@linuxbox ~]$ find ~ -type f | wc -l 38737
  Table 17-1 lists the common file-type tests supported by find. Table 17-1: find File Types
     File Type
  b c d f l
  Description
  Block special device file Character special device file Directory
  Regular file
  Symbolic link
            We can also search by file size and filename by adding some additional tests. Let’s look for all the regular files that match the wildcard pattern *.JPG and are larger than 1 megabyte:
  [me@linuxbox ~]$ find ~ -type f -name "*.JPG" -size +1M | wc -l 840
  In this example, we add the -name test followed by the wildcard pattern. Notice that we enclose it in quotes to prevent pathname expansion by the shell. Next, we add the -size test followed by the string +1M. The leading plus sign indicates that we are looking for files larger than the specified number. A leading minus sign would change the string to mean "smaller than the specified number." Using no sign means "match the value exactly." The trailing letter M indicates that the unit of measurement is megabytes. The characters shown in Table 17-2 may be used to specify units.
  Table 17-2: find Size Units
  Character Unit
  b 512-byte blocks (the default if no unit is specified)
  c Bytes
  w 2-byte words
  k Kilobytes (units of 1024 bytes)
  M Megabytes (units of 1,048,576 bytes)
  G Gigabytes (units of 1,073,741,824 bytes)
                 190 Chapter 17
  find supports a large number of different tests. Table 17-3 provides a rundown of the common ones. Note that in cases where a numeric argu- ment is required, the same + and - notation discussed above can be applied.
  Table 17-3: find Tests
   Test
  -cmin n
  -cnewer file -ctime n
  -empty -group name
  -iname pattern -inum n
  -mmin n -mtime n -name pattern -newer file
  -nouser
  -nogroup
  Description
  Match files or directories whose content or attributes were last modified exactly n minutes ago. To specify fewer than n minutes ago, use -n; to specify more than n minutes ago, use +n.
  Match files or directories whose contents or attributes were last modified more recently than those of file.
  Match files or directories whose contents or attributes (i.e., permissions) were last modified n*24 hours ago.
  Match empty files and directories.
  Match file or directories belonging to group name. name may be expressed as either a group name or as a numeric group ID.
  Like the -name test but case insensitive.
  Match files with inode number n. This is helpful for finding
  all the hard links to a particular inode.
  Match files or directories whose contents were modified n minutes ago.
  Match files or directories whose contents only were last modified n*24 hours ago.
  Match files and directories with the specified wildcard pattern.
  Match files and directories whose contents were modified more recently than the specified file. This is very useful when writing shell scripts that perform file backups. Each time you make a backup, update a file (such as a log) and then use find to determine which files have changed since the last update.
  Match file and directories that do not belong to a valid user. This can be used to find files belonging to deleted accounts or to detect activity by attackers.
  Match files and directories that do not belong to a valid group.
  (continued ) Searching for Files 191

  Table 17-3 (continued )
   Test
  -perm mode
  -samefile name
  -size n -type c -user name
  Description
  Match files or directories that have permissions set to the specified mode. mode may be expressed by either octal or symbolic notation.
  Similar to the -inum test. Matches files that share the same inode number as file name.
  Match files of size n. Match files of type c.
  Match files or directories belonging to name. name may be expressed by a username or by a numeric user ID.
            This is not a complete list. The find man page has all the details. Operators
  Even with all the tests that find provides, we may still need a better way to describe the logical relationships between the tests. For example, what if we needed to determine if all the files and subdirectories in a directory had secure permissions? We would look for all the files with permissions that are not 0600 and the directories with permissions that are not 0700. Fortunately, find provides a way to combine tests using logical operators to create more complex logical relationships. To express the aforementioned test, we could do this:
  [me@linuxbox ~]$ find ~ \( -type f -not -perm 0600 \) -or \( -type d -not -perm 0700 \)
  Yikes! That sure looks weird. What is all this stuff? Actually, the opera- tors are not that complicated once you get to know them (see Table 17-4).
  Table 17-4: find Logical Operators
  Operator Description
  -and Match if the tests on both sides of the operator are true. May be shortened to -a. Note that when no operator is present, -and is
  implied by default.
  -or Match if a test on either side of the operator is true. May be
  shortened to -o.
  -not Match if the test following the operator is false. May be shortened to -!.
           192 Chapter 17
  Table 17-4 (continued )
   Operator
  ( )
  Description
  Groups tests and operators together to form larger expressions. This is used to control the precedence of the logical evaluations. By default, find evaluates from left to right. It is often necessary to override the default evaluation order to obtain the desired result. Even if not needed, it is helpful sometimes to include the grouping characters to improve readability of the command. Note that since the parentheses characters have special meaning to the shell, they must be quoted when using them on the command line to allow them to be passed as arguments to find. Usually the backslash character is used to escape them.
    With this list of operators in hand, let’s deconstruct our find command. When viewed from the uppermost level, we see that our tests are arranged as two groupings separated by an -or operator:
  (expression 1) -or (expression 2)
  This makes sense, since we are searching for files with a certain set of permissions and for directories with a different set. If we are looking for both files and directories, why do we use -or instead of -and? Because as find scans through the files and directories, each one is evaluated to see if it matches the specified tests. We want to know if it is either a file with bad permissions or a directory with bad permissions. It can’t be both at the same time. So if we expand the grouped expressions, we can see it this way:
          (file with bad perms) -or (directory with bad perms)
  Our next challenge is how to test for "bad permissions." How do we do that? Actually we don’t. What we will test for is "not good permissions," since we know what "good permissions" are. In the case of files, we define good as 0600; for directories, 0700. The expression that will test files for "not good" permissions is:
          -type f -and -not -perms 0600
  and the expression for directories is:
          -type d -and -not -perms 0700
  As noted in Table 17-4, the -and operator can be safely removed, since it is implied by default. So if we put this all back together, we get our final command:
          find ~ (-type f -not -perms 0600) -or (-type d -not -perms 0700)
  However, since the parentheses have special meaning to the shell, we must escape them to prevent the shell from trying to interpret them. Pre- ceding each one with a backslash character does the trick.
  Searching for Files 193
  There is another feature of logical operators that is important to under- stand. Let’s say that we have two expressions separated by a logical operator:
  expr1 -operator expr2
  In all cases, expr1 will always be performed; however, the operator will
  determine if expr2 is performed. Table 17-5 shows how it works. Table 17-5: find AND/OR Logic
   Results of expr1 Operator True -and
  False -and
  True -or
  False -or
  expr2 is... Always performed Never performed Never performed Always performed
              Why does this happen? It’s done to improve performance. Take -and, for example. We know that the expression expr1 -and expr2 cannot be true if the result of expr1 is false, so there is no point in performing expr2. Likewise, if we have the expression expr1 -or expr2 and the result of expr1 is true, there is no point in performing expr2, as we already know that the expression expr1 -or expr2 is true.
  Okay, so this helps things go faster. Why is this important? Because we can rely on this behavior to control how actions are performed, as we shall soon see.
  Actions
  Let’s get some work done! Having a list of results from our find command is useful, but what we really want to do is act on the items on the list. Fortu- nately, find allows actions to be performed based on the search results.
  Predefined Actions
  There are a set of predefined actions and several ways to apply user-defined actions. First let’s look at a few of the predefined actions in Table 17-6.
  Table 17-6: Predefined find Actions
  Action Description
  -delete Delete the currently matching file.
  -ls Perform the equivalent of ls -dils on the matching file.
  Output is sent to standard output.
  -print Output the full pathname of the matching file to standard output. This is the default action if no other action is specified.
         194 Chapter 17
  Table 17-6 (continued ) Action Description
  -quit Quit once a match has been made.
  As with the tests, there are many more actions. See the find man page for full details.
  In our very first example, we did this:
  find ~
  This command produced a list of every file and subdirectory contained within our home directory. It produced a list because the -print action is implied if no other action is specified. Thus, our command could also be expressed as
  find ~ -print
  We can use find to delete files that meet certain criteria. For example, to delete files that have the file extension .BAK (which is often used to desig- nate backup files), we could use this command:
            find ~ -type f -name '*.BAK' -delete
  In this example, every file in the user’s home directory (and its sub- directories) is searched for filenames ending in .BAK. When they are found, they are deleted.
  Warning: It should go without saying that you should use extreme caution when using
  the -delete action. Always test the command first by substituting the -print action for -delete to confirm the search results.
  Before we go on, let’s take another look at how the logical operators affect actions. Consider the following command:
            find ~ -type f -name '*.BAK' -print
  As we have seen, this command will look for every regular file (-type f) whose name ends with .BAK (-name '*.BAK') and will output the relative path- name of each matching file to standard output (-print). However, the reason the command performs the way it does is determined by the logical relation- ships between each of the tests and actions. Remember, there is, by default, an implied -and relationship between each test and action. We could also express the command this way to make the logical relationships easier to see:
            find ~ -type f -and -name '*.BAK' -and -print
  With our command fully expressed, let’s look at Table 17-7 to see how the logical operators affect its execution.
                 Searching for Files 195
  Table 17-7: Effect of Logical Operators
   Test/Action
  -print
  -name '*.BAK'
  -type f
  Is performed when...
  -type f and -name '*.BAK' are true. -type f is true.
  Is always performed, since it is the first test/action in an -and relationship.
        Since the logical relationship between the tests and actions determines which of them are performed, we can see that the order of the tests and actions is important. For instance, if we were to reorder the tests and actions so that the -print action was the first one, the command would behave much differently:
  find ~ -print -and -type f -and -name '*.BAK'
  This version of the command will print each file (the -print action always evaluates to true) and then test for file type and the specified file extension.
  User-Defined Actions
  In addition to the predefined actions, we can also invoke arbitrary com- mands. The traditional way of doing this is with the -exec action, like this:
  -exec command {} ;
  where command is the name of a command, {} is a symbolic representation
  of the current pathname, and the semicolon is a required delimiter indicat- ing the end of the command. Here’s an example of using -exec to act like the -delete action discussed earlier:
  -exec rm '{}' ';'
  Again, since the brace and semicolon characters have special meaning to the shell, they must be quoted or escaped.
  It’s also possible to execute a user-defined action interactively. By using the -ok action in place of -exec, the user is prompted before execution of each specified command:
  find ~ -type f -name 'foo*' -ok ls -l '{}' ';'
  < ls ... /home/me/bin/foo > ? y
  -rwxr-xr-x 1 me me 224 2011-10-29 18:44 /home/me/bin/foo < ls ... /home/me/foo.txt > ? y
  -rw-r--r-- 1 me me 0 2012-09-19 12:53 /home/me/foo.txt
  In this example, we search for files with names starting with the string foo and execute the command ls -l each time one is found. Using the -ok action prompts the user before the ls command is executed.
        196 Chapter 17
  Improving Efficiency
  When the -exec action is used, it launches a new instance of the specified command each time a matching file is found. There are times when we might prefer to combine all of the search results and launch a single instance of the command. For example, rather than executing the commands like this,
  ls -l file1 ls -l file2
  we may prefer to execute them this way:
  ls -l file1 file2
  Here we cause the command to be executed only one time rather than multiple times. There are two ways we can do this: the traditional way, using the external command xargs, and the alternative way, using a new feature in find itself. We’ll talk about the alternative way first.
  By changing the trailing semicolon character to a plus sign, we activate the ability of find to combine the results of the search into an argument list for a single execution of the desired command. Going back to our example,
        find ~ -type f -name 'foo*' -exec ls -l '{}' ';'
  -rwxr-xr-x 1 me me 224 2011-10-29 18:44 /home/me/bin/foo -rw-r--r-- 1 me me 0 2012-09-19 12:53 /home/me/foo.txt
  will execute ls each time a matching file is found. By changing the com- mand to
        find ~ -type f -name 'foo*' -exec ls -l '{}' +
  -rwxr-xr-x 1 me me 224 2011-10-29 18:44 /home/me/bin/foo -rw-r--r-- 1 me me 0 2012-09-19 12:53 /home/me/foo.txt
  we get the same results, but the system has to execute the ls command only once.
  We can also use the xargs command to get the same result. xargs accepts input from standard input and converts it into an argument list for a speci- fied command. With our example, we would use it like this:
        find ~ -type f -name 'foo*' -print | xargs ls -l
  -rwxr-xr-x 1 me me 224 2011-10-29 18:44 /home/me/bin/foo -rw-r--r-- 1 me me 0 2012-09-19 12:53 /home/me/foo.txt
  Here we see the output of the find command piped into xargs, which, in turn, constructs an argument list for the ls command and then executes it.
  Note: While the number of arguments that can be placed into a command line is quite large, it’s not unlimited. It is possible to create commands that are too long for the shell to accept. When a command line exceeds the maximum length supported by the system, xargs executes the specified command with the maximum number of arguments pos- sible and then repeats this process until standard input is exhausted. To see the max- imum size of the command line, execute xargs with the --show-limits option.
        Searching for Files 197
     DEALING WITH FUNNY FILENAMES
  Unix-like systems allow embedded spaces (and even newlines!) in filenames. This causes problems for programs like xargs that construct argument lists for other programs. An embedded space will be treated as a delimiter, and the resulting command will interpret each space-separated word as a separate argument. To overcome this, find and xarg allow the optional use of a null char- acter as argument separator. A null character is defined in ASCII as the charac- ter represented by the number zero (as opposed to, for example, the space character, which is defined in ASCII as the character represented by the num- ber 32). The find command provides the action -print0, which produces null- separated output, and the xargs command has the --null option, which accepts null separated input. Here’s an example:
     find ~ -iname '*.jpg' -print0 | xargs --null ls -l
     Using this technique, we can ensure that all files, even those containing embedded spaces in their names, are handled correctly.
    A Return to the Playground
  It’s time to put find to some (almost) practical use. First, let’s create a play- ground with lots of subdirectories and files:

  [me@linuxbox ~]$ mkdir -p playground/dir-{00{1..9},0{10..99},100} [me@linuxbox ~]$ touch playground/dir-{00{1..9},0{10..99},100}/file-{A..Z}

  Marvel in the power of the command line! With these two lines, we cre- ated a playground directory containing 100 subdirectories, each containing 26 empty files. Try that with the GUI!

  The method we employed to accomplish this magic involved a familiar command (mkdir); an exotic shell expansion (braces); and a new command, touch. By combining mkdir with the -p option (which causes mkdir to create the parent directories of the specified paths) with brace expansion, we were able to create 100 directories.
  The touch command is usually used to set or update the modification times of files. However, if a filename argument is that of a non-existent file, an empty file is created.
  In our playground, we created 100 instances of a file named file-A. Let’s find them:
  [me@linuxbox ~]$ find playground -type f -name 'file-A'
  Note that unlike ls, find does not produce results in sorted order. Its order is determined by the layout of the storage device. We can confirm that we actually have 100 instances of the file this way:
  [me@linuxbox ~]$ find playground -type f -name 'file-A' | wc -l 100
        198 Chapter 17
  Next, let’s look at finding files based on their modification times. This will be helpful when creating backups or organizing files in chronological order. To do this, we will first create a reference file against which we will compare modification time:
  [me@linuxbox ~]$ touch playground/timestamp
  This creates an empty file named timestamp and sets its modification time to the current time. We can verify this by using another handy com- mand, stat, which is a kind of souped-up version of ls. The stat command reveals all that the system understands about a file and its attributes:
  [me@linuxbox ~]$ stat playground/timestamp
  File: `playground/timestamp'
  Size: 0 Blocks: 0 IO Block: 4096 regular empty file
  Device: 803h/2051d Inode: 14265061 Links: 1
  Access: (0644/-rw-r--r--)  Uid: ( 1001/ me)   Gid: ( 1001/ me)
  Access: 2012-10-08 15:15:39.000000000 -0400
  Modify: 2012-10-08 15:15:39.000000000 -0400
  Change: 2012-10-08 15:15:39.000000000 -0400
  If we touch the file again and then examine it with stat, we will see that the file’s times have been updated:
  [me@linuxbox ~]$ touch playground/timestamp [me@linuxbox ~]$ stat playground/timestamp
    File: `playground/timestamp'
  Size: 0 Blocks: 0 IO Block: 4096 regular empty file Device: 803h/2051d Inode: 14265061 Links: 1
  Access: (0644/-rw-r--r--) Uid: ( 1001/ me) Gid: ( 1001/ me) Access: 2012-10-08 15:23:33.000000000 -0400
  Modify: 2012-10-08 15:23:33.000000000 -0400
  Change: 2012-10-08 15:23:33.000000000 -0400
  Next, let’s use find to update some of our playground files: [me@linuxbox ~]$ find playground -type f -name 'file-B' -exec touch '{}' ';'
  This updates all files in the playground that are named file-B. Next we’ll use find to identify the updated files by comparing all the files to the refer- ence file timestamp:
  [me@linuxbox ~]$ find playground -type f -newer playground/timestamp
  The results contain all 100 instances of file-B. Since we performed
  a touch on all the files in the playground that are named file-B after we updated timestamp, they are now "newer" than timestamp and thus can be identified with the -newer test.
  Finally, let’s go back to the bad permissions test we performed earlier and apply it to playground:
  [me@linuxbox ~]$ find playground \( -type f -not -perm 0600 \) -or \( -type d -not -perm 0700 \)
              Searching for Files 199
  This command lists all 100 directories and 2,600 files in playground (as well as timestamp and playground itself, for a total of 2,702) because none of them meets our definition of "good permissions." With our knowledge of operators and actions, we can add actions to this command to apply new permissions to the files and directories in our playground:
  [me@linuxbox ~]$ find playground \( -type f -not -perm 0600 -exec chmod 0600 '{}' ';' \) -or \( -type d -not -perm 0700 -exec chmod 0700 '{}' ';' \)
  On a day-to-day basis, we might find it easier to issue two commands, one for the directories and one for the files, rather than this one large compound command, but it’s nice to know that we can do it this way. The important point here is to understand how operators and actions can be used together to perform useful tasks.
  Options
  Finally, we have the options. The options are used to control the scope of a find search. They may be included with other tests and actions when con- structing find expressions. Table 17-8 lists the most commonly used options.
  Table 17-8: find Options

  Option
  -depth
  -maxdepth levels -mindepth levels -mount
  -noleaf
  Description
  Direct find to process a directory’s files before the directory itself. This option is automatically applied when the -delete action is specified.
  Set the maximum number of levels that find will descend into a directory tree when performing tests and actions.
  Set the minimum number of levels that find will descend into a directory tree before applying tests and actions.
  Direct find not to traverse directories that are mounted on other filesystems.
  Direct find not to optimize its search based on the assumption that it is searching a Unix-like filesystem. This is needed when scanning DOS/Windows file- systems and CD-ROMs.

### VO 600w
  find is one of UNIX's most useful and important utilities. It finds files that match a given set of parameters, ranging from the file's name to its modification date.

  $ find path operators

  where path is the directory in which find will begin to search and operators (or, in more customary jargon, options ) tell find which files you're interested in. The operators are:

  -name   filename

  Find files with the given filename . This is the most commonly used operator. filename may include wildcards ( 15.2 ) , but if it does, it must be quoted to prevent the shell from interpreting the wildcards. See article 17.4 .

  -type   d

  *attibutes

  -perm   mode
  -user   name
  -group   name
  -size   n

  *time range
  -atime   n

  Find files that were accessed n days ago. + n means "find files that were accessed over n days ago" (i.e., not accessed in the last n days). - n means "find files that were accessed less than n days ago" (i.e., accessed in the last n days). See articles 17.5 and 17.7 .

  -mtime   n

  Similar to atime , except that it checks the time the file's contents were modified. See articles 17.5 and 17.7 .

  -ctime   n

  Similar to atime , except that it checks the time the inode ( 1.22 ) was last changed. "Changed" means that the file was modified or that one of its attributes (for example, its owner) was changed. See articles 17.5 and 17.7 .
  -newer   file

  Find files that have been modified more recently than the given file . See articles 17.8 and 17.9 .

  If you want to find a file that is seven days old, use the -mtime operator:

  $ find . -mtime 7 -print

  An alternate way is to specify a range of times:

  % find . -mtime +6 -mtime -8 -print

  mtime is the last modified time of a file. If you want to look for files that have not been used, check the access time with the -atime argument. A command to list all files that have not been read in 30 days or more is:

  $ find . -type f -atime +30 -print

  It is difficult to find directories that have not been accessed because the find command modifies the directory's access time.

  *operate on results

  -print
  -exec   command

   {} pathname of the file; must end with a backslash followed by a semicolon ( \;

  $ find -name "*.o" -exec rm -f {} \;

  tells find to delete any files whose names end in .o .

  -ok

  Same as -exec , except that find prompts you for permission before executing command . This is a useful way to test find commands. See article 17.10 .

  MP3 audio files scattered all over your filesystem; move them where you want. For example:

  $ find . -name '*.mp3' -print -exec mv '{}' ~/songs \;
  $ find . -name '*.mp3' -print -exec rm '{}' ~/songs \;

  $ -delete

  The -exec is a bit odd. Any filename making it this far will become part of a com- mand that is executed. The remainder of the lineup to the \; is the command to be executed. The {} is replaced by the name of the file that was found.

  *logical operators

  find -and -not -perms 0700

  find ~ (-type f -not -perms 0600) -or (-type d -not -perms 0700)
  -and
  -or
  -not

  *text search

  grep global regular expression print

  regular expressions describes patterns in text. similar to wildcards

  grep searches text files for the occurrence of a specified regular expression and outputs any line containing a match to standard output.
  [me@linuxbox ~]$ ls /usr/bin | grep zip

  This will list all the files in the /usr/bin directory whose names contain the substring zip.

  Option Description

  -i Ignore case. --ignore-case.

  -v Invert match.

  -c Print the number of matches instead of the lines themselves.

  -l
  Print the name of each file that contains a match instead of the lines

  -L
  Like the -l option, but print only the names of files that do not contain matches. May also be specified --files-without-match.

  -n Prefix each matching line with the number of the line within the file.

  -h For multifile searches, suppress the output of filenames.

  FURTHER EXPLORATION: mdfind, mdls, mdutil

## File modification 2m

  CRUD

  $ touch
  $ echo
  $ rm
  $ mkdir
  $ cp *-dt-*-nt-~
  $ cp foo.{txt,md}
  $ ln
  $ chown (permissions)
  $ chmod
  $ touch
  $ tar / gzip

  cat chap1 chap2 chap3 > book

  Redirection

  Function 	csh 	sh
  Send stdout to file 	prog > file 	prog > file
  Send stderr to file 		prog 2> file
  Send stdout and stderr to file 	prog >& file 	prog > file 2>&1
  Take stdin from file 	prog < file 	prog < file
  Send stdout to end of file 	prog >> file 	prog >> file
  Send stderr to end of file 		prog 2>> file
  Send stdout and stderr to end of file 	prog >>& file 	prog >> file 2>&1
  Read stdin from keyboard until c (see article 8.18 ) 	prog << c 	prog << c
  Pipe stdout to prog2 	prog | prog2 	prog | prog2
  Pipe stdout and stderr to prog2 	prog |& prog2 	prog 2>&1 | prog2

  { date; who; ls; } > log

  If you're running a program and you want to send its output to a file - but you want to see the output on your screen, too, so you can stop the program if something goes wrong - you can use tee . The tee program reads its standard input and writes it to one or more files. (The CD-ROM has the GNU version.)

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  There are times when it is useful to save the output of a command to a file, instead of displaying it to the screen. For example, if we want to create a file that lists all of the MP3 files in a directory, we can do something like this, using the ">" redirection character:

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt

  A similar command can be written so that instead of creating a new file called mp3files.txt,
  we can append to the end of the original file:
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  Reading, Writing, and Executing

  Access rights to files and directories are defined in terms of read access, write access, and execution access. If we look at the output of the ls com- mand, we can get some clue as to how this is implemented:
  [me@linuxbox ~]$ > foo.txt
  [me@linuxbox ~]$ ls -l foo.txt
  -rw-rw-r-- 1 me me 0 2012-03-06 14:52 foo.txt
     The first 10 characters of the listing are the file attributes (see Figure 9-1). The first of these characters is the file type. Table 9-1 lists the file types you are most likely to see (there are other, less common types too).
  The remaining nine characters of the file attributes, called the file mode, represent the read, write, and execute permissions for the file’s owner, the file’s group owner, and everybody else.
  Figure 9-1: Breakdow<!--  -->n of file attributes
   Permissions 79
  When set, the r, w, and x mode attributes have certain effects on files and directories, as shown in Table 9-2.
  Table 9-1: File Types
  Attribute File Type
  - A regular file.
  d A directory.
  l A symbolic link. Notice that with symbolic links, the remaining file attributes are always rwxrwxrwx and are dummy values. The real file attributes are those of the file the symbolic link points to.
  c A character special file. This file type refers to a device that handles data as a stream of bytes, such as a terminal or modem.
  b A block special file. This file type refers to a device that handles data in blocks, such as a hard drive or CD-ROM drive.

  Table 9-2: Permission Attributes
   Attribute
  Files
  Allows a file to be opened and read.
  Allows a file to be written to or trun- cated; however, this attribute does not allow files to be renamed or deleted. The ability to delete or rename files is determined by directory attributes.
  Allows a file to be treated as a pro- gram and executed. Program files writ- ten in scripting languages must also be set as readable to be executed.
  Directories
  Allows a directory’s contents to be listed if the execute attribute is also set.
  Allows files within a directory to be created, deleted, and renamed if the execute attribute is also set.
  Allows a directory to be entered; e.g.,
  cd directory.
  r
  w
  x
  Table 9-3: Permission Attribute Examples
           Table 9-3 shows some examples of file attribute settings.
   File Attributes
  -rwx------
  -rw-------
  Meaning
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.
  T
  able 9-3 (continued )
  File Attributes
  -rw-r--r--
  -rwxr-xr-x
  -rw-rw----
  Lrwxrwxrwx
  drwxrwx---
  drwxr-x---
  Meaning
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  chmod—Change File Mode

  To change the mode (permissions) of a file or directory, the chmod com- mand is used. Be aware that only the file’s owner or the superuser can change the mode of a file or directory. chmod supports two distinct ways of specifying mode changes: octal number representation and symbolic repres- entation. We will cover octal number representation first.

  Symbolic Representation
  chmod also supports a symbolic notation for specifying file modes. Symbolic notation is divided into three parts: whom the change will affect, which opera- tion will be performed, and which permission will be set. To specify who is affected, a combination of the characters u, g, o, and a is used, as shown in Table 9-5.
  Table 9-5: chmod Symbolic Notation

  Symbol
  u g o a
  Meaning
  Short for user but means the file or directory owner. Group owner.
  Short for others but means world.
  Short for all; the combination of u, g, and o.
          If no character is specified, all will be assumed. The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.
  Permissions are specified with the r, w, and x characters. Table 9-6 lists some examples of symbolic notation.
  Table 9-6: chmod Symbolic Notation Examples
  Notation Meaning
  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.
  (continued )

  Permissions 83
  Table 9-6 (continued )
  Notation
  o-rw go=rw
  u+x,go=rx
  Meaning
  Remove the read and write permissions from anyone besides the owner and group owner.
  Set the group owner and anyone besides the owner to have read and write permission. If either the group owner or world previously had execute permissions, remove them.
  Add execute permission for the owner and set the permissions for the group and others to read and execute. Multiple speci- fications may be separated by commas.
        84 Chapter 9

  Some people prefer to use octal notation; some folks really like the sym- bolic. Symbolic notation does offer the advantage of allowing you to set a single attribute without disturbing any of the others.
  Take a look at the chmod man page for more details and a list of options. A word of caution regarding the --recursive option: It acts on both files and directories, so it’s not as useful as one would hope because we rarely want files and directories to have the same permissions.

  chown—Change File Owner and Group

  The chown command is used to change the owner and group owner of a file or directory. Superuser privileges are required to use this command. The syntax of chown looks like this:

  chown [owner][:[group]] file...
  chown can change the file owner and/or the file group owner depending
  on the first argument of the command. Table 9-7 lists some examples.
  Table 9-7: chown Argument Examples
  Argument
  bob
  bob:users
  :admins
  bob:
  Results
  Changes the ownership of the file from its current owner to user bob.
  Changes the ownership of the file from its current owner to user bob and changes the file group owner to group users.
  Changes the group owner to the group admins. The file owner is unchanged.
  Change the file owner from the current owner to user bob and changes the group owner to the login group of user bob.

  Undo with sudo

  e.g. PostgreSQL user
  e.g. shell script


### VO 300w
  (create day,month,year files & directories)

  we cre- ated a playground directory containing 100 subdirectories, each containing 26 empty files

  $ mkdir -p playground/dir-{00{1..9},0{10..99},100}
  $ touch playground/dir-{00{1..9},0{10..99},100}/file-{A..Z}

  *redirection

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  save the output of a command to a file, instead of displaying it to the screen.

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  { date; who; ls; } > log

  *change file attritutes

  -rwx------
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.

  -rw-r--r--
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.

  -rwxr-xr-x
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.

  -rw-rw----
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.

  Lrwxrwxrwx
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.

  drwxrwx---
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.

  drwxr-x---
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  *change file mode

  u Short for user but means the file or directory owner.
  g Group owner.
  o Short for others but means world.
  a Short for all; the combination of u, g, and o.

  If no character is specified, all will be assumed.

  The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.

  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.

  *change file owner

  chown [owner][:[group]]
  chown -R

  SELF DIRECTED:
  * chmod octal

## Text processing 4m

  34.24 Quick Reference: sed

  How sed operates:

      Each line of input is copied into a pattern space.

      Editing commands may be given on the command line (if more than one, use a -e option before each command) and/or in script files named after -f options. All editing commands are applied in order to each line of input.

      Editing commands are applied to all lines (globally) unless line addressing restricts the lines affected.

      If a command changes the input, subsequent command-addresses will be applied to the current line in the pattern space, not the original input line.

      The original input file is unchanged; editing commands modify a copy of the original input line. The copy is sent to standard output ( 13.1 ) unless the -n option was used; standard output can be redirected to a file ( 13.1 , 34.3 ) .

  34.24.1 Syntax of sed Commands

  sed commands have the general form:

      [ address ][ , address ][ ! ] command [ arguments ]

  sed commands consist of addresses and editing commands . commands consist of a single letter or symbol; they are described later, alphabetically and by group. arguments include the label supplied to b or t , the filename supplied to r or w , and the substitution flags for s . addresses are described below. Elements in [ brackets ] are optional; don't type the brackets.

  Braces ( {} ) are used in sed to nest one address inside another or to apply multiple commands at the same address:

      [

      address

      ][
      ,


      address

      ]{


      command1
         command2


      }

  The left curly brace ( { ) is a command that starts a group of other sed commands. The group ends with a right curly brace ( } ). Commands within the braces may be spread across multiple lines, as shown above. Or commands may be on the same line, with a semicolon ( ; ) after each command (including the last command on a line) - as in:

      [ address ][ , address ] { command1 ; ... commandN ; }

  34.24.2 Pattern Addressing

  A sed command can specify zero, one, or two addresses. An address can be a line number, the symbol $ (for last line), or a regular expression enclosed in slashes ( / pattern / ). Regular expressions are described in Chapter 26, Regular Expressions (Pattern Matching) . Additionally, \n can be used to match any newline in the pattern space (resulting from the N command), but not the newline at the end of the pattern space. See article 34.4 .
  If the command specifies: 	Then it is applied to:
  No address

  Each input line.
  One address

  Any line matching the address. Some commands accept only one address: a , i , r , q , and = .
  Two comma-separated addresses

  First matching line and all succeeding lines up to and including a line matching the second address. Repeat for each matching range in the text.
  An address followed by !

  All lines that do not match the address.
  34.24.2.1 Examples

  Substitute on all lines (all occurrences):

      s/xx/yy/g

  Delete lines containing BSD :

      /BSD/d

  Print the lines between each pair of BEGIN and END , inclusive:

      /^BEGIN/,/^END/p

  Delete any line that doesn't contain SAVE :

      /SAVE/!d

  Substitute on all lines, except between BEGIN and END :

      /BEGIN/,/END/!s/xx/yy/g

  34.24.3 Alphabetical Summary of sed Commands

  #

      Begin a comment in a sed script. If the first such line is exactly #n , sed sets its -n command-line option.
  :

      : label

      Label a line in the script for the transfer of control by b or t . label may contain up to seven characters.
  =

      [ address ] =

      Write to standard output the line number of each line addressed.
  a

          [ address ]a\
          text

      Append text following each line matched by address . If there is more than one line of text , all newlines except the last must be "hidden" by preceding them with a backslash. text will be terminated by the first newline that is not hidden in this way. text is not available in the pattern space, and subsequent commands cannot be applied to it. The results of this command are sent to standard output when the list of editing commands is finished, regardless of what happens to the current line in the pattern space. (There's an example in article 43.22 , among others.)

      Example

          $a\
          This goes after the last line in the file\
          (marked by $). This text is escaped at the\
          end of each line, except for the last one.

  b

      [ address1 ][, address2 ] b[ label ]

      Transfer control unconditionally to : label elsewhere in script. That is, the command following the label is the next command applied to the current line. If no label is specified, control falls through to the end of the script, so no more commands are applied to the current line. See articles 34.19 and 34.17 .

      Example

          # Ignore tbl tables; resume script after TE:
          /^\.TS/,/^\.TE/b

  c

          [ address1 ][ , address2 ]c\
          text

      Replace the lines selected by the address with text . When a range of lines is specified, all lines as a group are replaced by a single copy of text . The newline following each line of text must be escaped by a backslash, except the last line. The contents of the pattern space are, in effect, deleted and no subsequent editing commands can be applied to it (or text ).

      Example

          # Replace first 100 lines in a file:
          1,100c\

          ...first replacement line
          \

          ...second replacement line
          \

          ...
          \

          ...last replacement line

  d

      [ address1 ][, address2 ]d

      Delete the addressed line (or lines) from the pattern space. Thus, the line is not passed to standard output. A new line of input is read, and editing resumes with the first command in the script. See articles 34.4 and 34.18 .

      Example

          # delete all blank lines:
          /^$/d

  D

      [ address1 ][ , address2 ] D

      Delete first part (up to embedded newline) of multiline pattern space created by N command and resume editing with first command in script. If this command empties the pattern space, then a new line of input is read, as if d had been executed. See article 34.18 .

      Example

          # Strip multiple blank lines, leaving only one:
          /^$/{
              N
              /^\n$/D
          }

  g

      [ address1 ][, address2 ]g

      Paste the contents of the hold space (see h or H ) back into the pattern space, wiping out the previous contents of the pattern space. See articles 34.13 and 34.16 . The example shows a simple way to copy lines.

      Example

      This script collects all lines containing the word Item: and copies them to a place marker later in the file. The place marker is overwritten.

          /Item:/H
          /<Replace this line with the item list>/g

  G

      [ address1 ][ , address2 ] G

      Same as g , except that the hold space is pasted below the address instead of overwriting it. The example shows a simple way to "cut and paste" lines. See articles 34.13 and 34.16 .

      Example

      This script collects all lines containing the word Item: and moves them after a place marker later in the file. The original Item: lines are deleted.

          /Item:/{
              H
              d
          }
          /Summary of items:/G

  h

      [ address1 ][ , address2 ] h Copy the pattern space into the hold space, a special temporary buffer. The previous contents of the hold space are obliterated. You can use h to save a line before editing it. See articles 34.13 and 34.16 .

      Example

          # Edit a line; print the change; replay the original
          /UNIX/{
              h
              s/.* UNIX \(.*\) .*/\1:/
              p
              x
          }

      Sample input:

          This describes the UNIX ls command.
          This describes the UNIX cp command.

      Sample output:

          ls:
          This describes the UNIX ls command.
          cp:
          This describes the UNIX cp command.

  H

      [ address1 ][ , address2 ] H

      Append the contents of the pattern space (preceded by a newline) to the contents of the hold space. Even if the hold space is empty, H still appends a newline. H is like an incremental copy. See examples under g and G , also articles 34.13 and 34.16 .
  i

          [ address ]i\
          text

      Insert text before each line matched by address . (See a for details on text .) Article 43.20 shows a script that uses i .

      Example

          /Item 1/i\
          The five items are listed below:

  l

      [ address1 ][ , address2 ] l

      List the contents of the pattern space, showing non-printing characters as ASCII codes ( 51.3 , 25.7 ) . Long lines are wrapped.
  n

      [ address1 ][ , address2 ] n

      Read next line of input into pattern space. The current line is sent to standard output, and the next line becomes the current line. Control passes to the command following n instead of resuming at the top of the script.

      Example

      In the ms macros ( 43.14 ) , a section header occurs on the line below an .NH macro. To print all lines of header text, invoke this script with sed -n :

          /^\.NH/{
              n
              p
          }

  N

      [ address1 ][ , address2 ] N

      Append next input line to contents of pattern space; the two lines are separated by an embedded newline. (This command is designed to allow pattern matches across two lines.) Using \n to match the embedded newline, you can match patterns across multiple lines. See example under D , also article 34.15 .

      Examples

      Like previous example, but print .NH line as well as header title:

          /^\.NH/{
              N
              p
          }

      Join two lines (replace newline with space):

          /^\.NH/{
              N
              s/\n/ /
              p
          }

  p

      [ address1 ][ , address2 ] p

      Print the addressed line(s). Unless the -n command-line option is used, this command will cause duplicate lines to be output. Also, it is typically used before commands that change flow control ( d , N , b ) and that might prevent the current line from being output. See examples under h , n , and N .
  P

      [ address1 ][ , address2 ] P

      Print first part (up to embedded newline) of multiline pattern created by N command. Same as p if N has not been applied to a line.

      Example

      The following script prints each line containing word and also the line before it:

          N
          /

          word

          /P
          D

  q

      [ address ] q

      Quit when address is encountered. The addressed line is first written to output (if default output is not suppressed), along with any text appended to it by previous a or r commands. See articles 34.21 and 34.22 .

      Example

      Delete everything after the addressed line:

          /Garbled text follows:/q

      Print only the first 50 lines of a file:

          50q

  r

      [ address ] r file

      Read contents of file and append after the contents of the pattern space. Exactly one space must be put between the r and file .

      Example

          /The list of items follows:/r item_file

  s

      [ address1 ][ , address2 ] s/ pattern / replacement / [ flags ]

      Substitute replacement for pattern on each addressed line. If pattern addresses are used, the pattern // represents the last pattern address specified. The following flags can be specified:

      n

          Replace n th instance of / pattern / on each addressed line. n is any number in the range 1 to 512 (default is 1). See article 34.11 .
      g

          Replace all instances of / pattern / on each addressed line, not just the first instance.
      p

          Print the line if a successful substitution is done. If several successful substitutions are done, multiple copies of the line will be printed. Often used in scripts with the -n command-line option ( 34.2 ) .
      w  file

          Write the line to a file if a replacement was done. A maximum of ten different files can be opened in a script. See articles 34.7 through 34.10 .

          Examples

          Here are some short, commented scripts:

              # Change third and fourth quote to ( and ):
              /function/{
                  s/"/)/4
                  s/"/(/3
              }

              # Remove all quotes on a given line:
              /Title/s/"//g

              # Remove first colon or all quotes; print resulting lines:
              s/://p
              s/"//gp

              # Change first "if" but leave "ifdef" alone:
              /ifdef/!s/if/   if/

  t

      [ address1 ][ , address2 ] t [ label ]

      Test if any substitutions have been made on addressed lines, and if so, branch to line marked by : label . (See b and : .) If label is not specified, control falls through to bottom of script. See article 34.20 .

      The t command can be used like a case statement ( 44.5 ) in the Bourne shell. You test each case: when it's true, you exit the construct.

      Example

      Suppose you want to fill empty fields of a database. You have this:

          ID: 1   Name: greg   Rate: 45
          ID: 2   Name: dale
          ID: 3

      You want this:

          ID: 1   Name: greg   Rate: 45   Phone: ??
          ID: 2   Name: dale   Rate: ??   Phone: ??
          ID: 3   Name: ????   Rate: ??   Phone: ??

      You need to test the number of fields already there. Here's the script (fields are tab-separated):

          /ID/{
              s/ID: .* Name: .* Rate: .*/&   Phone: ??/p
              t
              s/ID: .* Name: .*/&   Rate: ??   Phone: ??/p
              t
              s/ID: .*/&   Name: ??     Rate: ??   Phone: ??/p
          }

  w

      [ address1 ][ , address2 ] w file

      Append, contents of pattern space to file . This action occurs when the command is encountered rather than when the pattern space is output. Exactly one space must separate the w and file . A maximum of ten different files can be opened in a script. This command will create the file if it does not exist; if the file exists, its contents will be overwritten each time the script is executed. Multiple write commands that direct output to the same file append to the end of the file.

      Example

          # Store tbl and eqn blocks in a file:
          /^\.TS/,/^\.TE/w troff_stuff
          /^\.EQ/,/^\.EN/w troff_stuff

  x

      [ address1 ][ , address2 ] x

      Exchange contents of the pattern space with the contents of the hold space. For examples, see h and articles 34.13 and 34.16 .
  y

      [ address1 ][ , address2 ] y/ abc / xyz /

      Translate characters. Change every instance of a to x , b to y , c to z , etc. See articles 34.12 and 34.14 .

      Example

          # Change item 1, 2, 3 to Item A, B, C ...
          /^item [1-9]/y/i123456789/IABCDEFGHI/


  Pipes and Filters

  We’ve seen how to redirect input from a file and output to a file. You can also connect two programs together so the output from one program becomes the input of the next, without ever being written to disk. Two or more programs connected in this way form a pipe. To make a pipe, place a vertical bar (|) on the command line between the two commands.
  When a pipe is set up between two commands, the standard output of the command to the left of the pipe symbol becomes the standard input of the command to the right of the pipe symbol. Any two commands can form a pipe, as long as the first program writes to standard output and the second program reads from standard input. For example:
  $ ls -l $HOME | colrm 1 30 714 Jul 29 23:16 Desktop
      1020 Jul 19 23:39 Documents
       238 Jul 30 07:22 Downloads
       408 Jul 28 07:14 Dropbox
       714 Jul 24 08:47 Google Drive
      1768 Jul 29 23:00 Library
       340 Jul 26 14:54 Movies
       204 Jul 19 22:53 Music
       408 Jul 24 11:59 Pictures
      1938 Jul  9 16:52 Presentations
       170 Jul 19 10:04 Public
       408 Jul 20 07:20 bin
   Pipes and Filters
  | 141
  This example combines ls -l with the colrm (column remove) command to give you a listing that just includes file size, modification date, and name.
  You could take this example one step further and redirect its output to a file; for example:
  $ ls -l | colrm 1 30 > homedirlist.txt
  That command line starts by listing the files, uses colrm to strip out the extraneous information that ls -l returns, and then redirects the re­ maining information into a new file, named homedirlist.txt.
  You just can’t do that in the Finder.
  When a program takes its input from another program, performs some operation on that input, and writes the result to the standard output (or pipes it to yet another pro­ gram), it is referred to as a filter. A common use of filters is to modify output. Just as a common filter culls unwanted items, Unix filters can restructure output so you get just what you need.
  Most Unix programs can be used to form pipes. Some programs that are commonly used as filters are described in the next sections. (Note that these programs aren’t used only as filters or parts of pipes, though; they’re also useful in their own right.)
  wc
  The wc program is one of the most useful pipe programs, believe it or not. By default, the program counts characters, words, and lines in the input file or standard input, but you can constrain the output to just characters (-c), words (-w), or lines (-l). Counting lines turns out to be wonderfully useful.
  A classic example is identifying how many "core" files are in the filesystem.
  Core files are identified with the suffix .core; they’re crashed program debugging datafiles and can be deleted to free up disk space as needed.
  This is done with a call to find with the output piped to wc:
  $ sudo find / -name "*.core" -print | wc -l 13
  $
  sudo helps sidestep any permissions problems here.
     142 | Chapter 6: Redirecting I/O
  A more common use of find and wc together is to count larger output streams. For example, wondering how many directories you have within your Documents directory? You might be surprised:
  $ find ~/Documents -type d -print | wc -l 1064
  You can see how having a single number displayed is far superior to having all 1,064 directory names stream past!
  tr
  Another simple and helpful program for command pipes is tr, the translator utility. The most common use for this command is to replace all occurrences of one character with another character. Here’s how you would replace all occurrences of x with y:
  tr "x" "y"
  More usefully, tr can also work with sets of characters (you can either list them all in a range or specify a named range like lower or alpha), so it’s an easy way to turn all low­ ercase text into uppercase:
      tr "[:lower:]" "[:upper:]" < file1
  For example:
  $ tr "[:lower:]" "[:upper:]" < todo 1. WAKE UP
  2. LOOK IN MIRROR
  3. SIGH
      4. GO BACK TO BED.
      $
  The tr command has a number of different options for power users, including -c to invert the specified pattern (that is, if you specify tr -c "abc", the program matches anything other than a, b, or c), and -d deletes any characters from the first pattern specified.
  To remove all vowels from the input, you could use:
  $ tr -d "[aeiou]" < todo 1. Wk p
  2. Lk n mrrr
  3. Sgh
  4. G bck t bd.
  The tr command can be quite useful in other situations, too. Wondering how many words appear in a large text file? tr can figure this out with a little help from the -s flag, which tells it to output only one occurrence of a character if more than one is found:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | wc -l 29061
   Pipes and Filters | 143
  Here, we can see that Lewis Carroll’s Alice’s Adventures in Wonderland contains just over 29,000 words.
  You can download this text for yourself at http://www.intuitive.com/ wicked/scripts/alice.txt.gz.
  As with the wc command, tr may not seem too useful by itself, but when you start building up more complex pipes you’ll be surprised by how frequently it’s useful to translate case and fix similar problems.
  grep
  As you learned in the previous chapter, grep searches the contents of files for lines that contain a certain pattern. The syntax is:
  grep "pattern" file(s)
  Most of the earlier discussion, however, focused on how grep can help you search through files to find lines that match a specified pattern. In fact, grep is a tremendously useful command for pipes, too, because it can help you easily weed out the few lines you care about from hundreds or thousands of lines of information.
  As an example, let’s use the mdfind command to identify files on the system that reference the word "ipod" (mdfind, a part of Spotlight, is discussed in Chapter 5). The default command reveals that there are 1,030 matches, by using wc:
  $ mdfind ipod | wc -l 1030
  It turns out that many of these are actually related to the scripting Automator utility and other library files. They’re easily identified by their Library directory location, however, so grep, with its useful -v option (which returns everything but lines that match this pattern) helps us identify how many files aren’t in the Library subdirectory:
  $ mdfind ipod | grep -v "Library" | wc -l 150
  Of those 150, how many are within my home directory?
  $ mdfind ipod | grep -v "Library" | grep "/taylor/" | wc -l 82
  Notice here that you can build pipes that are 2, 3, 4, or even 10 or 20 commands long. Unix has no limit on how complex your pipes can be, and I commonly work with pipes that are six or seven commands long.
    144 | Chapter 6: Redirecting I/O
  head and tail
  When you have output of hundreds or thousands of lines, being able to peek in and see the first few or last few lines is critically important. Those two tasks are enabled by the helpful head and tail commands. With both commands, the default action is to show 10 lines (the first 10 for head, and the last 10 for tail). You can change this by specifying n, where n is the desired number of lines. To see just the first three lines, use head -3, and to see the last 15, use tail -15.
  For example, we can see that the last 15 words of Alice’s Adventures in Wonderland are:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | tail -15
      in
      all
      their
      simple
      joys
      remembering
      her
      own
      child
      life
      and
      the
      happy
      summer
      days
      $
  In addition to using head and tail to view the beginning or end of files, with a little bit of fancy footwork, you can use them to view any range of lines in a file. Want to see lines 131−134? You could use:
  $ head -134 alice.txt | tail -4
  Alice opened the door and found that it led into a small passage, not much larger than a rat-hole: she knelt down and looked along the passage into the loveliest garden you ever saw. How she longed to get out of that dark hall, and wander about among those beds of $
  This could also be accomplished by using other Unix commands, and that’s part of the power of Unix: there’s usually more than one way to solve a problem at the command line.
  sort
  The sort program arranges lines of text alphabetically or numerically. The following example alphabetically sorts the lines in the food file. sort doesn’t modify the file itself; it just reads the file and displays the result on standard output (in this case, the Terminal):
   Pipes and Filters | 145
  $ sort food Afghani Cuisine Bangkok Wok Big Apple Deli Isle of Java Mandalay
      Sushi and Sashimi
      Sweet Tooth
      Tio Pepe's Peppers
  By default, sort arranges lines of text alphabetically. Many options control the sorting, and Table 6-1 lists some of them.
  Table 6-1. Some sort options
  Option Description
  -n Sort numerically (for example, 10 sorts after 2); ignore blanks and tabs. -r Reverse the sorting order.
  -f Sort upper- and lowercase together.
  -kx Ignore firstxfields when sorting.
  Don’t forget that more than two commands may be linked together with a pipe. Taking a previous pipe example using grep, you can further sort the files modified in January by order of size. The following pipe uses the commands ls, grep, and sort:
  $ ls -l | grep "Jan" | sort -n -k 5
  drwx------ 2 taylor taylor 264 Jan 13 10:02 Music/ drwx------ 4 taylor taylor 264 Jan 29 22:33 Movies/ drwxr-xr-x 3 taylor taylor 264 Jan 24 21:24 Public/ drwx------ 95 taylor taylor 3186 Jan 29 22:44 Pictures/ $
  Both grep and sort are used here as filters to modify the output of the ls -l command. This pipe sorts all files in your working directory modified in January by order of size, and prints them to the Terminal screen. The sort option -n forces a numeric (rather than alphabetic) sort, and -k 5 uses the fifth field as the sort key. So, the output of ls, filtered by grep, is sorted by the file size (this is the fifth column, starting with 264).
  sort is also a powerful tool for identifying the extremes of a list. A common use is to identify the largest files on the system, which can be done by using find and xargs to generate a list of all files, one per line, including their size in 512-byte blocks, then feeding that to sort -rn (reverse, numeric) and looking at the top few:
  $ find . -type f -print0 | xargs -0 ls -s1 | sort -rn | head 14082048 ./Documents/Parallels/Ubuntu Linux 11.04 Desktop.pvm/
          ubuntu-linux-11.04-desktop-amd64-0.hdd/ubuntu-linux-11.04-desktop-amd...
      9474040 ./Music/iTunes/iTunes Media/Movies/Lawrence of Arabia/Lawrence of Ara...
      6316920 ./Music/iTunes/iTunes Media/Movies/Who Framed Roger Rabbit/Who Framed...
      6129352 ./Music/iTunes/iTunes Media/Movies/Dial 'M' For Murder/Dial 'M' For M...
      5774616 ./Music/iTunes/iTunes Media/Movies/Casablanca/Casablanca.mp4
      146
  | Chapter 6: Redirecting I/O
      5766976 ./Music/iTunes/iTunes Media/Movies/Tomb Raider - The Cradle of Life/T...
      5764848 ./Music/iTunes/iTunes Media/Movies/In The Shadow of the Moon/In The S...
      5559592 ./Documents/Entourage Mail Data/Database
      5559592 ./Documents/Microsoft User Data/Office 2008 Identities/
          Main Identity/Database
      5409584 ./Music/iTunes/iTunes Media/Movies/Tomb Raider/Tomb Raider.mp4
  Coupled with the power of find, you should be able to see how you can identify not only the largest files, but also the largest files owned by a particular user (hint: use find - user XX to match all files owned by that user).
  uniq
  Another command that’s quite useful in pipes is the oddly named uniq (which would be easier to remember if it were spelled correctly: unique). Give uniq a stream of input, and it silently eliminates duplicate lines. Add the -c flag, and uniq not only removes duplicate lines but lists a count of how frequently each line occurs.
  If you’re thinking that sort and uniq are a good pair, you’re absolutely correct! For ex­ ample, figuring out how many unique words occur in the book Alice’s Adventures in Wonderland is a simple task:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | uniq | wc -l 27313
  Or is it? That’s not correct, because in this situation, uniq needs to have the input sorted. Add that step and the number changes dramatically:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | sort | uniq | wc -l 2868
  Further, we should also ensure that all the letters are lowercase, so that "Hello" and "hello," for example, are counted as one word, not two. This can be done by using the - f (ignore case) flag to sort:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | sort -f | uniq | wc -l 2577
  So now you know—the entire novel is written using only 2,577 different words.
  Piping Output to a Pager
  The less program, which you saw in Chapter 4, can also be used as a filter. A long output normally zips by you on the screen, but if you run text through less, the display stops after each page or screen of text (that’s why such programs are called pagers: they let you see the output page by page).
   Pipes and Filters | 147
  Let’s assume that you have a long directory listing. (If you want to try this example and need a directory with lots of files, use cd first to change to a system directory such as /bin or /usr/bin.) To make it easier to read the sorted listing, pipe the output through less:
  $ cd /bin
  $ ls -l | sort -nk 5 | less
  total 5976
  -rwxr-xr-x 1 root wheel
  -rwxr-xr-x 1 root wheel
  -r-xr-xr-x 1 root wheel
  -rwxr-xr-x 1 root wheel
  -r-xr-xr-x 1 root wheel
  -rwxr-xr-x 1 root wheel
  ...
  -rwxr-xr-x 1 root wheel 566144 May 5 18:54 zsh -r-xr-xr-x 1 root wheel 1333792 May 5 21:18 bash -r-xr-xr-x 1 root wheel 1333872 May 5 21:18 sh -r-xr-xr-x 1 root wheel 1380176 May 5 21:18 ksh
  less reads a screen of text from the pipe (consisting of lines sorted by order of file size), then prints a colon (:) prompt. At the prompt, you can type a less command to move through the sorted text. less reads more text from the pipe, shows it to you, and saves a copy of what it has read, so you can go backward to reread previous text if you want. When you’re done viewing the sorted text, type the q command at the colon prompt to quit less. Table 6-2 contains a list of useful commands to use along with less.
  Table 6-2. Useful less commands to remember
  Command Meaning
  d
  u
  b
  f /pat ?pat n
  :n v q
  Scroll down (forward) one half of the screen size. Scroll up (backward) one half the screen size. Scroll back one screen.
  Scroll forward one screen.
  Scroll forward until a line containing the specified pattern is found. Scroll back until a line containing the specified pattern is found.
  Repeat previous search.
  Move to the next file in the file list (if more than one file was specified). Open up the file in the vi editor.
  Quit.
  13984 May  5 18:54 sleep
  14048 May  5 18:54 echo
  14064 May  5 21:18 wait4path
  14096 May  5 21:18 rmdir
  14192 May  5 18:54 domainname
  14192 May  5 18:54 pwd

  sort—Sort Lines of Text Files
  The sort program sorts the contents of standard input, or one or more files specified on the command line, and sends the results to standard output. Using the same technique that we used with cat, we can demonstrate pro- cessing of standard input directly from the keyboard.
  [me@linuxbox ~]$ sort > foo.txt c
  b
  a
  [me@linuxbox ~]$ cat foo.txt a
  b
  c
      236 Chapter 20
  After entering the command, we type the letters c, b, and a, followed once again by CTRL-D to indicate end-of-file. We then view the resulting file and see that the lines now appear in sorted order.
  Since sort can accept multiple files on the command line as arguments, it is possible to merge multiple files into a single sorted whole. For example, if we had three text files and wanted to combine them into a single sorted file, we could do something like this:
  sort file1.txt file2.txt file3.txt > final_sorted_list.txt
  sort has several interesting options. Table 20-1 shows a partial list.
  Table 20-1: Common sort Options
  Option Long Option
   -b         --ignore-leading-blanks
  -f --ignore-case -n --numeric-sort
  -r --reverse
  -k --key=field1[,field2]
  -m --merge
  -o --output=file
  -t --field-separator=char
  Description
  By default, sorting is performed on the entire line, starting with the first char- acter in the line. This option causes sort to ignore leading spaces in lines and calculates sorting based on the first non-whitespace character on the line.
  Makes sorting case insensitive.
  Performs sorting based on the numeric evaluation of a string. Using this option allows sorting to be performed on numeric values rather than alphabetic values.
  Sort in reverse order. Results are in descending rather than ascending order.
  Sort based on a key field located from field1 to field2 rather than the entire line.
  Treat each argument as the name of a presorted file. Merge multiple files into a single sorted result without perform- ing any additional sorting.
  Send sorted output to file rather than to standard output.
  Define the field-separator character. By default, fields are separated by spaces or tabs.
                             Text Processing 237
  Although most of the options above are pretty self-explanatory, some are not. First, let’s look at the -n option, used for numeric sorting. With this option, it is possible to sort values based on numeric values. We can demon- strate this by sorting the results of the du command to determine the largest users of disk space. Normally, the du command lists the results of a summary in pathname order:
  [me@linuxbox ~]$ du -s /usr/share/* | head 252 /usr/share/aclocal
  96 /usr/share/acpi-support
  8 /usr/share/adduser
  196 /usr/share/alacarte 344 /usr/share/alsa
  8 /usr/share/alsa-base 12488 /usr/share/anthy
  8 /usr/share/apmd
  21440 /usr/share/app-install
   48
  /usr/share/application-registry
   In this example, we pipe the results into head to limit the results to the first 10 lines. We can produce a numerically sorted list to show the 10 largest consumers of space this way:
  [me@linuxbox ~]$ du -s /usr/share/* | sort -nr | head 509940 /usr/share/locale-langpack
  242660 /usr/share/doc
  197560 /usr/share/fonts
  179144 /usr/share/gnome 146764 /usr/share/myspell 144304 /usr/share/gimp 135880 /usr/share/dict 76508 /usr/share/icons 68072 /usr/share/apps 62844 /usr/share/foomatic
  By using the -nr options, we produce a reverse numerical sort, with the largest values appearing first in the results. This sort works because the numerical values occur at the beginning of each line. But what if we want to sort a list based on some value found within the line? For example, the result of ls -l looks like this:
  [me@linuxbox ~]$ ls -l /usr/bin | head total 152948
     -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
   34824 2012-04-04 02:42 [
  101556 2011-11-27 06:08 a2p
   13036 2012-02-27 08:22 aconnect
   10552 2011-08-15 10:34 acpi
    3800 2012-04-14 03:51 acpi_fakekey
    7536 2012-04-19 00:19 acpi_listen
    3576 2012-04-29 07:57 addpart
   20808 2012-01-03 18:02 addr2line
  489704 2012-10-09 17:02 adept_batch
   238 Chapter 20
  Ignoring, for the moment, that ls can sort its results by size, we could use sort to sort this list by file size, as well.
   [me@linuxbox ~]$ ls -l /usr/bin | sort -nr -k 5 | head
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  8234216 2012-04-07 17:42 inkscape
  8222692 2012-04-07 17:42 inkview
  3746508 2012-03-07 23:45 gimp-2.4
  3654020 2012-08-26 16:16 quanta
  2928760 2012-09-10 14:31 gdbtui
  2928756 2012-09-10 14:31 gdb
  2602236 2012-10-10 12:56 net
  2304684 2012-10-10 12:56 rpcclient
  2241832 2012-04-04 05:56 aptitude
  2202476 2012-10-10 12:56 smbcacls
   Many uses of sort involve the processing of tabular data, such as the results of the ls command above. If we apply database terminology to the table above, we would say that each row is a record and that each record con- sists of multiple fields, such as the file attributes, link count, filename, file size and so on. sort is able to process individual fields. In database terms,
  we are able to specify one or more key fields to use as sort keys. In the example above, we specify the n and r options to perform a reverse numerical sort and specify -k 5 to make sort use the fifth field as the key for sorting.
  The k option is very interesting and has many features, but first we need to talk about how sort defines fields. Let’s consider a very simple text file consisting of a single line containing the author’s name:
  William    Shotts
  By default, sort sees this line as having two fields. The first field contains the characters William and the second field contains the characters Shotts, meaning that whitespace characters (spaces and tabs) are used as delimiters between fields and that the delimiters are included in the field when sorting is performed.
  Looking again at a line from our ls output, we can see that a line con- tains eight fields and that the fifth field is the file size:
  -rwxr-xr-x 1 root   root    8234216 2012-04-07 17:42 inkscape
  For our next series of experiments, let’s consider the following file con- taining the history of three popular Linux distributions released from 2006 to 2008. Each line in the file has three fields: the distribution name, the ver- sion number, and the date of release in MM/DD/YYYY format:
       SUSE
  Fedora
  SUSE
  Ubuntu
  Fedora
  SUSE
  Ubuntu
  Fedora
  Ubuntu
  Ubuntu
  SUSE
  Fedora
  10.2 12/07/2006 10 11/25/2008 11.0 06/19/2008 8.04 04/24/2008 8 11/08/2007 10.3 10/04/2007 6.10 10/26/2006 7 05/31/2007 7.10 10/18/2007 7.04 04/19/2007 10.1 05/11/2006 6 10/24/2006
  Text Processing 239
  Fedora
  Ubuntu
  Ubuntu
  Fedora
  9 05/13/2008 6.06 06/01/2006 8.10 10/30/2008 5 03/20/2006
   Using a text editor (perhaps vim), we’ll enter this data and name the resulting file distros.txt.
  Next, we’ll try sorting the file and observe the results:
  [me@linuxbox ~]$ sort distros.txt
   Fedora
  Fedora
  Fedora
  Fedora
  Fedora
  Fedora
  SUSE
  SUSE
  SUSE
  SUSE
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  10 11/25/2008 5 03/20/2006 6 10/24/2006 7 05/31/2007 8 11/08/2007 9 05/13/2008 10.1 05/11/2006 10.2 12/07/2006 10.3 10/04/2007 11.0 06/19/2008 6.06 06/01/2006 6.10 10/26/2006 7.04 04/19/2007 7.10 10/18/2007 8.04 04/24/2008 8.10 10/30/2008
   Well, it mostly worked. The problem occurs in the sorting of the Fedora version numbers. Since a 1 comes before a 5 in the character set, version 10 ends up at the top while version 9 falls to the bottom.
  To fix this problem, we have to sort on multiple keys. We want to per- form an alphabetic sort on the first field and then a numeric sort on the third field. sort allows multiple instances of the -k option so that multiple sort keys can be specified. In fact, a key may include a range of fields. If no range is specified (as has been the case with our previous examples), sort uses a key that begins with the specified field and extends to the end of the line.
  Here is the syntax for our multikey sort:
  [me@linuxbox ~]$ sort --key=1,1 --key=2n distros.txt
   Fedora
  Fedora
  Fedora
  Fedora
  Fedora
  Fedora
  SUSE
  SUSE
  SUSE
  SUSE
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  5 03/20/2006 6 10/24/2006 7 05/31/2007 8 11/08/2007 9 05/13/2008 10 11/25/2008 10.1 05/11/2006 10.2 12/07/2006 10.3 10/04/2007 11.0 06/19/2008 6.06 06/01/2006 6.10 10/26/2006 7.04 04/19/2007 7.10 10/18/2007 8.04 04/24/2008 8.10 10/30/2008
   240 Chapter 20
  Though we used the long form of the option for clarity, -k 1,1 -k 2n would be exactly equivalent. In the first instance of the key option, we spe- cified a range of fields to include in the first key. Since we wanted to limit the sort to just the first field, we specified 1,1, which means "start at field 1 and end at field 1." In the second instance, we specified 2n, which means that field 2 is the sort key and that the sort should be numeric. An option letter may be included at the end of a key specifier to indicate the type of sort to be performed. These option letters are the same as the global options for the sort program: b (ignore leading blanks), n (numeric sort), r (reverse sort), and so on.
  The third field in our list contains a date in an inconvenient format for sorting. On computers, dates are usually formatted in YYYY-MM-DD order to make chronological sorting easy, but ours are in the American format of MM/DD/YYYY. How can we sort this list in chronological order?
  Fortunately, sort provides a way. The key option allows specification of offsets within fields, so we can define keys within fields:
  [me@linuxbox ~]$ sort -k 3.7nbr -k 3.1nbr -k 3.4nbr distros.txt
   Fedora
  Ubuntu
  SUSE
  Fedora
  Ubuntu
  Fedora
  Ubuntu
  SUSE
  Fedora
  Ubuntu
  SUSE
  Ubuntu
  Fedora
  Ubuntu
  SUSE
  Fedora
  10 11/25/2008 8.10 10/30/2008 11.0 06/19/2008 9 05/13/2008 8.04 04/24/2008 8 11/08/2007 7.10 10/18/2007 10.3 10/04/2007 7 05/31/2007 7.04 04/19/2007 10.2 12/07/2006 6.10 10/26/2006 6 10/24/2006 6.06 06/01/2006 10.1 05/11/2006 5 03/20/2006
   By specifying -k 3.7, we instruct sort to use a sort key that begins at the seventh character within the third field, which corresponds to the start of the year. Likewise, we specify -k 3.1 and -k 3.4 to isolate the month and day portions of the date. We also add the n and r options to achieve a reverse numeric sort. The b option is included to suppress the leading spaces (whose numbers vary from line to line, thereby affecting the outcome of the sort) in the date field.
  Some files don’t use tabs and spaces as field delimiters; take, for example, the /etc/passwd file:
  [me@linuxbox ~]$ head /etc/passwd root:x:0:0:root:/root:/bin/bash daemon:x:1:1:daemon:/usr/sbin:/bin/sh bin:x:2:2:bin:/bin:/bin/sh sys:x:3:3:sys:/dev:/bin/sh sync:x:4:65534:sync:/bin:/bin/sync games:x:5:60:games:/usr/games:/bin/sh man:x:6:12:man:/var/cache/man:/bin/sh
   Text Processing 241
        lp:x:7:7:lp:/var/spool/lpd:/bin/sh
        mail:x:8:8:mail:/var/mail:/bin/sh
        news:x:9:9:news:/var/spool/news:/bin/sh
  The fields in this file are delimited with colons (:), so how would we sort this file using a key field? sort provides the -t option to define the field separator character. To sort the passwd file on the seventh field (the account’s default shell), we could do this:
  [me@linuxbox ~]$ sort -t ':' -k 7 /etc/passwd | head me:x:1001:1001:Myself,,,:/home/me:/bin/bash root:x:0:0:root:/root:/bin/bash dhcp:x:101:102::/nonexistent:/bin/false
  gdm:x:106:114:Gnome Display Manager:/var/lib/gdm:/bin/false hplip:x:104:7:HPLIP system user,,,:/var/run/hplip:/bin/false klog:x:103:104::/home/klog:/bin/false messagebus:x:108:119::/var/run/dbus:/bin/false polkituser:x:110:122:PolicyKit,,,:/var/run/PolicyKit:/bin/false pulse:x:107:116:PulseAudio daemon,,,:/var/run/pulse:/bin/false
  By specifying the colon character as the field separator, we can sort on the seventh field.
  uniq—Report or Omit Repeated Lines
  Compared to sort, the uniq program is a lightweight. uniq performs a seem- ingly trivial task. When given a sorted file (including standard input), it removes any duplicate lines and sends the results to standard output. It is often used in conjunction with sort to clean the output of duplicates.
  Note: While uniq is a traditional Unix tool often used with sort, the GNU version of sort supports a -u option, which removes duplicates from the sorted output.
  Let’s make a text file to try this out:
  [me@linuxbox ~]$ cat > foo.txt a
  b
  c
  a b c
  Remember to type CTRL-D to terminate standard input. Now, if we run uniq on our text file, the results are no different from our original file; the duplicates were not removed:
  [me@linuxbox ~]$ uniq foo.txt a
  b
  c
  a b c
         242 Chapter 20
  For uniq to actually do its job, the input must be sorted first:
  [me@linuxbox ~]$ sort foo.txt | uniq a
  b
  c
  This is because uniq only removes duplicate lines that are adjacent to each other.
  uniq has several options. Table 20-2 lists the common ones. Table 20-2: Common uniq Options
     Option
  -c -d
  -f n
  -i -s n -u
  Description
  Output a list of duplicate lines preceded by the number of times the line occurs.
  Output only repeated lines, rather than unique lines.
  Ignore n leading fields in each line. Fields are separated by whitespace as they are in sort; however, unlike sort, uniq has no option for setting an alternative field separator.
  Ignore case during the line comparisons.
  Skip (ignore) the leading n characters of each line. Output only unique lines. This is the default.
              Here we see uniq used to report the number of duplicates found in our text file, using the -c option:
  [me@linuxbox ~]$ sort foo.txt | uniq -c 2a
  2b 2c
  Slicing and Dicing
  The next three programs we will discuss are used to peel columns of text out of files and recombine them in useful ways.
  cut—Remove Sections from Each Line of Files
  The cut program is used to extract a section of text from a line and output the extracted section to standard output. It can accept multiple file argu- ments or input from standard input.
  Specifying the section of the line to be extracted is somewhat awkward and is specified using the options shown in Table 20-3.
    Text Processing 243
  Table 20-3: cut Selection Options
   Option
  -c char_list
  -f field_list
  -d delim_char
  --complement
  Description
  Extract the portion of the line defined by char_list. The list may consist of one or more comma-separated numerical ranges.
  Extract one or more fields from the line as defined by field_list. The list may contain one or more fields or field ranges separated by commas.
  When -f is specified, use delim_char as the field delimit- ing character. By default, fields must be separated by a single tab character.
  Extract the entire line of text, except for those portions specified by -c and/or -f.
          As we can see, the way cut extracts text is rather inflexible. cut is best used to extract text from files that are produced by other programs, rather than text directly typed by humans. We’ll take a look at our distros.txt file to see if it is "clean" enough to be a good specimen for our cut examples. If we use cat with the -A option, we can see if the file meets our requirements of tab-separated fields.
  [me@linuxbox ~]$ cat -A distros.txt SUSE^I10.2^I12/07/2006$ Fedora^I10^I11/25/2008$ SUSE^I11.0^I06/19/2008$ Ubuntu^I8.04^I04/24/2008$ Fedora^I8^I11/08/2007$ SUSE^I10.3^I10/04/2007$ Ubuntu^I6.10^I10/26/2006$ Fedora^I7^I05/31/2007$ Ubuntu^I7.10^I10/18/2007$ Ubuntu^I7.04^I04/19/2007$ SUSE^I10.1^I05/11/2006$ Fedora^I6^I10/24/2006$ Fedora^I9^I05/13/2008$ Ubuntu^I6.06^I06/01/2006$ Ubuntu^I8.10^I10/30/2008$ Fedora^I5^I03/20/2006$
  It looks good—no embedded spaces, just single tab characters between the fields. Since the file uses tabs rather than spaces, we’ll use the -f option to extract a field:
  [me@linuxbox ~]$ cut -f 3 distros.txt 12/07/2006
  11/25/2008
  06/19/2008
  04/24/2008
  11/08/2007
     244 Chapter 20
  10/04/2007
  10/26/2006
  05/31/2007
  10/18/2007
  04/19/2007
  05/11/2006
  10/24/2006
  05/13/2008
  06/01/2006
  10/30/2008
  03/20/2006
  Because our distros file is tab delimited, it is best to use cut to extract fields rather than characters. This is because when a file is tab delimited, it is unlikely that each line will contain the same number of characters, which makes calculating character positions within the line difficult or impossible. In our example above, however, we now have extracted a field that luckily contains data of identical length, so we can show how character extraction works by extracting the year from each line:
  [me@linuxbox ~]$ cut -f 3 distros.txt | cut -c 7-10 2006
  2008
  2008
  2008
  2007
  2007
  2006
  2007
  2007
  2007
  2006
  2006
  2008
  2006
  2008
  2006
  By running cut a second time on our list, we are able to extract charac- ter positions 7 through 10, which corresponds to the year in our date field. The 7-10 notation is an example of a range. The cut man page contains a complete description of how ranges can be specified.
  When working with fields, it is possible to specify a different field delim- iter rather than the tab character. Here we will extract the first field from the /etc/passwd file:
  [me@linuxbox ~]$ cut -d ':' -f 1 /etc/passwd | head root
  daemon
  bin
  sys
  sync
  games
  man
      Text Processing 245
  lp mail news
  Using the -d option, we are able to specify the colon character as the field delimiter.
      EXPANDING TABS
  Our distros.txt file is ideally formatted for extracting fields using cut. But what if we wanted a file that could be fully manipulated with cut by characters, rather than fields? This would require us to replace the tab characters within the file with the corresponding number of spaces. Fortunately, the GNU coreutils pack- age includes a tool for that. Named expand, this program accepts either one or more file arguments or standard input, and it outputs the modified text to standard output.
  If we process our distros.txt file with expand, we can use the cut -c to extract any range of characters from the file. For example, we could use the follow- ing command to extract the year of release from our list by expanding the file and using cut to extract every character from the 23rd position to the end of the line:
       [me@linuxbox ~]$ expand distros.txt | cut -c 23-
     coreutils also provides the unexpand program to substitute tabs for spaces.
    paste—Merge Lines of Files
  The paste command does the opposite of cut. Rather than extracting a column of text from a file, it adds one or more columns of text to a file.
  It does this by reading multiple files and combining the fields found in each file into a single stream of standard output. Like cut, paste accepts multiple file arguments and/or standard input. To demonstrate how paste operates, we will perform some surgery on our distros.txt file to produce a chronological list of releases.
  From our earlier work with sort, we will first produce a list of distros sorted by date and store the result in a file called distros-by-date.txt:
  [me@linuxbox ~]$ sort -k 3.7nbr -k 3.1nbr -k 3.4nbr distros.txt > distros-by- date.txt
  Next, we will use cut to extract the first two fields from the file (the dis- tro name and version) and store that result in a file named distro-versions.txt:
  [me@linuxbox ~]$ cut -f 1,2 distros-by-date.txt > distros-versions.txt [me@linuxbox ~]$ head distros-versions.txt
     246 Chapter 20
  Fedora 10 Ubuntu 8.10 SUSE 11.0 Fedora 9 Ubuntu 8.04 Fedora 8 Ubuntu 7.10 SUSE 10.3 Fedora 7 Ubuntu 7.04
  The final piece of preparation is to extract the release dates and store them a file named distro-dates.txt:
  [me@linuxbox ~]$ cut -f 3 distros-by-date.txt > distros-dates.txt [me@linuxbox ~]$ head distros-dates.txt
  11/25/2008
  10/30/2008
  06/19/2008
  05/13/2008
  04/24/2008
  11/08/2007
  10/18/2007
  10/04/2007
  05/31/2007
  04/19/2007
  We now have the parts we need. To complete the process, use paste to put the column of dates ahead of the distro names and versions, thus creat- ing a chronological list. This is done simply by using paste and ordering its arguments in the desired arrangement.
  [me@linuxbox ~]$ paste distros-dates.txt distros-versions.txt
      11/25/2008
  10/30/2008
  06/19/2008
  05/13/2008
  04/24/2008
  11/08/2007
  10/18/2007
  10/04/2007
  05/31/2007
  04/19/2007
  12/07/2006
  10/26/2006
  10/24/2006
  06/01/2006
  05/11/2006
  03/20/2006
  Fedora 10 Ubuntu 8.10 SUSE 11.0 Fedora 9 Ubuntu 8.04 Fedora 8 Ubuntu 7.10 SUSE 10.3 Fedora 7 Ubuntu 7.04 SUSE 10.2 Ubuntu 6.10 Fedora 6 Ubuntu 6.06 SUSE 10.1 Fedora 5
   join—Join Lines of Two Files on a Common Field
  In some ways, join is like paste in that it adds columns to a file, but it does so in a unique way. A join is an operation usually associated with relational data- bases where data from multiple tables with a shared key field is combined to
  Text Processing 247
  form a desired result. The join program performs the same operation. It joins data from multiple files based on a shared key field.
  To see how a join operation is used in a relational database, let’s ima- gine a very small database consisting of two tables, each containing a single record. The first table, called CUSTOMERS, has three fields: a customer number (CUSTNUM), the customer’s first name (FNAME), and the cus- tomer’s last name (LNAME):
   CUSTNUM
  =========
  4681934
  FNAME LNAME ====== ====== John Smith
   The second table is called ORDERS and contains four fields: an order number (ORDERNUM), the customer number (CUSTNUM), the quantity (QUAN), and the item ordered (ITEM):
   ORDERNUM
  ==========
  3014953305
  CUSTNUM
  =========
  4681934
  QUAN ITEM
  ===== ====
  1 Blue Widget
   Note that both tables share the field CUSTNUM. This is important, as it allows a relationship between the tables.
  Performing a join operation would allow us to combine the fields in the two tables to achieve a useful result, such as preparing an invoice. Using the matching values in the CUSTNUM fields of both tables, a join operation could produce the following:
  FNAME LNAME QUAN ITEM
  ====== ====== ===== ====
  John Smith 1 Blue Widget
  To demonstrate the join program, we’ll need to make a couple of files with a shared key. To do this, we will use our distros-by-date.txt file. From this file, we will construct two additional files. One contains the release dates (which will be our shared key field for this demonstration) and the release names:
  [me@linuxbox ~]$ cut -f 1,1 distros-by-date.txt > distros-names.txt [me@linuxbox ~]$ paste distros-dates.txt distros-names.txt > distros-key-names .txt
  [me@linuxbox ~]$ head distros-key-names.txt
     11/25/2008
  10/30/2008
  06/19/2008
  05/13/2008
  04/24/2008
  11/08/2007
  10/18/2007
  10/04/2007
  05/31/2007
  04/19/2007
  Fedora
  Ubuntu
  SUSE
  Fedora
  Ubuntu
  Fedora
  Ubuntu
  SUSE
  Fedora
  Ubuntu
   248 Chapter 20
  The second file contains the release dates and the version numbers:
  [me@linuxbox ~]$ cut -f 2,2 distros-by-date.txt > distros-vernums.txt [me@linuxbox ~]$ paste distros-dates.txt distros-vernums.txt > distros-key- vernums.txt
  [me@linuxbox ~]$ head distros-key-vernums.txt
  11/25/2008 10 10/30/2008 8.10 06/19/2008 11.0 05/13/2008 9 04/24/2008 8.04 11/08/2007 8 10/18/2007 7.10 10/04/2007 10.3 05/31/2007 7 04/19/2007 7.04
  We now have two files with a shared key (the "release date" field). It is important to point out that the files must be sorted on the key field for join to work properly.
  [me@linuxbox ~]$ join distros-key-names.txt distros-key-vernums.txt | head 11/25/2008 Fedora 10
  10/30/2008 Ubuntu 8.10
  06/19/2008 SUSE 11.0
               05/13/2008 Fedora 9
               04/24/2008 Ubuntu 8.04
               11/08/2007 Fedora 8
               10/18/2007 Ubuntu 7.10
               10/04/2007 SUSE 10.3
               05/31/2007 Fedora 7
               04/19/2007 Ubuntu 7.04
  Note also that, by default, join uses whitespace as the input field delim- iter and a single space as the output field delimiter. This behavior can be modified by specifying options. See the join man page for details.

  tr—Transliterate or Delete Characters

  The tr program is used to transliterate characters. We can think of this as a sort of character-based search-and-replace operation. Transliteration is the process of changing characters from one alphabet to another. For example, converting characters from lowercase to uppercase is transliteration. We can perform such a conversion with tr as follows:
  [me@linuxbox ~]$ echo "lowercase letters" | tr a-z A-Z LOWERCASE LETTERS
  As we can see, tr operates on standard input and outputs its results on standard output. tr accepts two arguments: a set of characters to convert from and a corresponding set of characters to convert to. Character sets may be expressed in one of three ways:
    An enumerated list; for example, ABCDEFGHIJKLMNOPQRSTUVWXYZ.
    A character range; for example, A-Z. Note that this method is sometimes subject to the same issues as other commands (due to the locale colla- tion order) and thus should be used with caution.
    POSIX character classes; for example, [:upper:].
  In most cases, the character sets should be of equal length; however, it is possible for the first set to be larger than the second, particularly if we wish to convert multiple characters to a single character:
  [me@linuxbox ~]$ echo "lowercase letters" | tr [:lower:] A AAAAAAAAA AAAAAAA
  In addition to transliteration, tr allows characters to simply be deleted from the input stream. Earlier in this chapter, we discussed the problem of converting MS-DOS text files to Unix-style text. To perform this conversion, carriage return characters need to be removed from the end of each line. This can be performed with tr as follows:
  tr -d '\r' < dos_file > unix_file
      254
  Chapter 20
  where dos_file is the file to be converted and unix_file is the result. This form of the command uses the escape sequence \r to represent the carriage return character. To see a complete list of the sequences and character classes tr supports, try
  [me@linuxbox ~]$ tr –help
       ROT13: THE NOT-SO-SECRET DECODER RING
  One amusing use of tr is to perform ROT13 encoding of text. ROT13 is a trivial type of encryption based on a simple substitution cipher. Calling ROT13 encryp- tion is being generous; text obfuscation is more accurate. It is used sometimes on text to obscure potentially offensive content. The method simply moves each character 13 places up the alphabet. Since this is halfway up the possible 26 characters, performing the algorithm a second time on the text restores it to
  its original form. To perform this encoding with tr:
     echo "secret text" | tr a-zA-Z n-za-mN-ZA-M
  frperg grkg
     Performing the same procedure a second time results in the translation:
   echo "frperg grkg" | tr a-zA-Z n-za-mN-ZA-M
  secret text
     A number of email programs and Usenet news readers support ROT13 encoding. Wikipedia contains a good article on the subject: http://en.wikipedia .org/wiki/ROT13.
    tr can perform another trick, too. Using the -s option, tr can "squeeze" (delete) repeated instances of a character:
  [me@linuxbox ~]$ echo "aaabbbccc" | tr -s ab abccc
  Here we have a string containing repeated characters. By specifying
  the set ab to tr, we eliminate the repeated instances of the letters in the set, while leaving the character that is missing from the set (c) unchanged. Note that the repeating characters must be adjoining. If they are not, the squeez- ing will have no effect:
  [me@linuxbox ~]$ echo "abcabcabc" | tr -s ab abcabcabc
      Text Processing 255
  sed—Stream Editor for Filtering and Transforming Text
  The name sed is short for stream editor. It performs text editing on a stream of text, either a set of specified files or standard input. sed is a powerful and somewhat complex program (there are entire books about it), so we will not cover it completely here.
  In general, the way sed works is that it is given either a single editing command (on the command line) or the name of a script file containing multiple commands, and it then performs these commands upon each line in the stream of text. Here is a very simple example of sed in action:
  [me@linuxbox ~]$ echo "front" | sed 's/front/back/' back
  In this example, we produce a one-word stream of text using echo and pipe it into sed. sed, in turn, carries out the instruction s/front/back/ upon the text in the stream and produces the output back as a result. We can also recognize this command as resembling the substitution (search and replace) command in vi.
  Commands in sed begin with a single letter. In the example above, the substitution command is represented by the letter s and is followed by the search and replace strings, separated by the slash character as a delimiter. The choice of the delimiter character is arbitrary. By convention, the slash character is often used, but sed will accept any character that immediately follows the command as the delimiter. We could perform the same com- mand this way:
  [me@linuxbox ~]$ echo "front" | sed 's_front_back_' back
  When the underscore character is used immediately after the command, it becomes the delimiter. The ability to set the delimiter can be used to make commands more readable, as we shall see.
  Most commands in sed may be preceded by an address, which specifies which line(s) of the input stream will be edited. If the address is omitted, then the editing command is carried out on every line in the input stream. The simplest form of address is a line number. We can add one to our example:
  [me@linuxbox ~]$ echo "front" | sed '1s/front/back/' back
  Adding the address 1 to our command causes our substitution to be performed on the first line of our one-line input stream. We can specify another number:
  [me@linuxbox ~]$ echo "front" | sed '2s/front/back/' front
          256 Chapter 20
  Now we see that the editing is not carried out, because our input stream does not have a line 2.
  Addresses may be expressed in many ways. Table 20-7 lists the most common ones.
  Table 20-7: sed Address Notation
   Address
  n
  $ /regexp/
  addr1,addr2 first~step
  addr1,+n addr!
  Description
  A line number where n is a positive integer
  The last line
  Lines matching a POSIX basic regular expression. Note that the regular expression is delimited by slash characters. Optionally, the regular expression may be delimited by an alternate char- acter, by specifying the expression with \cregexpc, where c is the alternate character.
  A range of lines from addr1 to addr2, inclusive. Addresses may be any of the single address forms above.
  Match the line represented by the number first and then each subsequent line at step intervals. For example, 1~2 refers to each odd-numbered line, and 5~5 refers to the fifth line and every fifth line thereafter.
  Match addr1 and the following n lines.
  Match all lines except addr, which may be any of the forms above.
                We’ll demonstrate different kinds of addresses using the distros.txt file from earlier in this chapter. First, a range of line numbers:
  [me@linuxbox ~]$ sed -n '1,5p' distros.txt
   SUSE
  Fedora
  SUSE
  Ubuntu
  Fedora
  10.2
  10
  11.0
  8.04
  8
  12/07/2006
  11/25/2008
  06/19/2008
  04/24/2008
  11/08/2007
   we print a range of lines, starting with line 1 and con- do this, we use the p command, which simply causes
  In this example,
  tinuing to line 5. To
  a matched line to be printed. For this to be effective, however, we must include the option -n (the no autoprint option) to cause sed not to print every line by default.
  Text Processing 257
  Next, we’ll try a regular expression:
  [me@linuxbox ~]$ sed -n '/SUSE/p' distros.txt
   SUSE 10.2 SUSE 11.0 SUSE 10.3 SUSE 10.1
  12/07/2006
  06/19/2008
  10/04/2007
  05/11/2006
   By including the slash-delimited regular expression /SUSE/, we are able to isolate the lines containing it in much the same manner as grep.
  Finally, we’ll try negation by adding an exclamation point (!) to the address:
  [me@linuxbox ~]$ sed -n '/SUSE/!p' distros.txt
   Fedora
  Ubuntu
  Fedora
  Ubuntu
  Fedora
  Ubuntu
  Ubuntu
  Fedora
  Fedora
  Ubuntu
  Ubuntu
  Fedora
  10 11/25/2008 8.04 04/24/2008 8 11/08/2007 6.10 10/26/2006 7 05/31/2007 7.10 10/18/2007 7.04 04/19/2007 6 10/24/2006 9 05/13/2008 6.06 06/01/2006 8.10 10/30/2008 5 03/20/2006
   Here we see the expected result: all of the lines in the file except the ones matched by the regular expression.
  So far, we’ve looked at two of the sed editing commands, s and p. Table 20-8 is a more complete list of the basic editing commands.
  Table 20-8: sed Basic Editing Commands
  Command Description
  = Output current line number.
  a Append text after the current line.
  d Delete the current line.
  i Insert text in front of the current line.
  p Print the current line. By default, sed prints every line and edits only lines that match a specified address
  within the file. The default behavior can be over- ridden by specifying the -n option.
  q Exit sed without processing any more lines. If the -n option is not specified, output the current line.
               258 Chapter 20
  Table 20-8 (continued )
  Command
  Q s/regexp/replacement/
  Description
  Exit sed without processing any more lines.
  Substitute the contents of replacement wherever regexp is found. replacement may include the special character &, which is equivalent to the text matched by regexp. In addition, replacement may include the sequences \1 through \9, which are the contents of the corresponding subexpressions in regexp. For more about this, see the following discussion on back references. After the trailing slash following replacement, an optional flag may be specified to modify the s command’s behavior.
  Perform transliteration by converting characters from set1 to the corresponding characters in set2. Note that unlike tr, sed requires that both sets be of the same length.
       y/set1/set2
    The s command is by far the most commonly used editing command. We will demonstrate just some of its power by performing an edit on our distros.txt file. We discussed before how the date field in distros.txt was not in a "computer-friendly" format. While the date is formatted MM/DD/YYYY,
  it would be better (for ease of sorting) if the format were YYYY-MM-DD. To perform this change on the file by hand would be both time consuming and error prone, but with sed, this change can be performed in one step:
  [me@linuxbox ~]$ sed 's/\([0-9]\{2\}\)\/\([0-9]\{2\}\)\/\([0-9]\{4\}\)$/\3-\1
   -\2/' distros.txt
  SUSE 10.2
  2006-12-07
  2008-11-25
  2008-06-19
  2008-04-24
  2007-11-08
  2007-10-04
  2006-10-26
  2007-05-31
  2007-10-18
  2007-04-19
  2006-05-11
  2006-10-24
  2008-05-13
  2006-06-01
  2008-10-30
  2006-03-20
  Fedora
  SUSE
  Ubuntu
  Fedora
  SUSE
  Ubuntu
  Fedora
  Ubuntu
  Ubuntu
  SUSE
  Fedora
  Fedora
  Ubuntu
  Ubuntu
  Fedora
  10
  11.0
  8.04
  8
  10.3
  6.10
  7
  7.10
  7.04
  10.1
  6
  9 6.06 8.10 5
   Wow! Now that is an ugly-looking command. But it works. In just one step, we have changed the date format in our file. It is also a perfect example of why regular expressions are sometimes jokingly referred to as a "write-only"
  Text Processing 259
  260 Chapter 20
  medium. We can write them, but we sometimes cannot read them. Before we are tempted to run away in terror from this command, let’s look at how it was constructed. First, we know that the command will have this basic structure:
  sed 's/regexp/replacement/' distros.txt
  Our next step is to figure out a regular expression that will isolate the date. Since it is in MM/DD/YYYY format and appears at the end of the line, we can use an expression like this:
          [0-9]{2}/[0-9]{2}/[0-9]{4}$
  which matches two digits, a slash, two digits, a slash, four digits, and the end of line. So that takes care of regexp, but what about replacement? To handle that, we must introduce a new regular expression feature that appears in some applications that use BRE. This feature is called back references and works like this: If the sequence \n appears in replacement where n is a number from one to nine, the sequence will refer to the corresponding subexpression in the preceding regular expression. To create the subexpressions, we simply enclose them in parentheses like so:
          ([0-9]{2})/([0-9]{2})/([0-9]{4})$
  We now have three subexpressions. The first contains the month, the second contains the day of the month, and the third contains the year. Now we can construct replacement as follows:
  \3-\1-\2
  which gives us the year, a dash, the month, a dash, and the day. Now, our command looks like this:
  sed 's/([0-9]{2})/([0-9]{2})/([0-9]{4})$/\3-\1-\2/' distros.txt
  We have two remaining problems. The first is that the extra slashes in our regular expression will confuse sed when it tries to interpret the s com- mand. The second is that since sed, by default, accepts only basic regular expressions, several of the characters in our regular expression will be taken as literals, rather than as metacharacters. We can solve both these problems with a liberal application of backslashes to escape the offending characters:
  sed 's/\([0-9]\{2\}\)\/\([0-9]\{2\}\)\/\([0-9]\{4\}\)$/\3-\1-\2/' dis tros.txt
  And there you have it!
  Another feature of the s command is the use of optional flags that may follow the replacement string. The most important of these is the g flag, which instructs sed to apply the search and replace globally to a line, not just to the first instance, which is the default.
  Here is an example:
  [me@linuxbox ~]$ echo "aaabbbccc" | sed 's/b/B/' aaaBbbccc
  We see that the replacement was performed but only to the first instance of the letter b, while the remaining instances were left unchanged. By adding the g flag, we are able to change all the instances:
  [me@linuxbox ~]$ echo "aaabbbccc" | sed 's/b/B/g' aaaBBBccc
  So far, we have given sed single commands only via the command line. It is also possible to construct more complex commands in a script file using the -f option. To demonstrate, we will use sed with our distros.txt file to build a report. Our report will feature a title at the top, our modified dates, and all the distribution names converted to uppercase. To do this, we will need to write a script, so we’ll fire up our text editor and enter the following:
  # sed script to produce Linux distributions report
  1 i\
  \
  Linux Distributions Report\
  s/\([0-9]\{2\}\)\/\([0-9]\{2\}\)\/\([0-9]\{4\}\)$/\3-\1-\2/ y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/
  We will save our sed script as distros.sed and run it like this: [me@linuxbox ~]$ sed -f distros.sed distros.txt
  Linux Distributions Report
         SUSE
  FEDORA
  SUSE
  UBUNTU
  FEDORA
  SUSE
  UBUNTU
  FEDORA
  UBUNTU
  UBUNTU
  SUSE
  FEDORA
  FEDORA
  UBUNTU
  UBUNTU
  FEDORA
  10.2 2006-12-07 10 2008-11-25 11.0 2008-06-19 8.04 2008-04-24 8 2007-11-08 10.3 2007-10-04 6.10 2006-10-26 7 2007-05-31 7.10 2007-10-18 7.04 2007-04-19 10.1 2006-05-11 6 2006-10-24 9 2008-05-13 6.06 2006-06-01 8.10 2008-10-30 5 2006-03-20
   Text Processing 261
  As we can see, our script produces the desired results, but how does it do it? Let’s take another look at our script. We’ll use cat to number the lines.
  [me@linuxbox ~]$ cat -n distros.sed
  1 # sed script to produce Linux distributions report 2
  3 1i\
  4\
  5 Linux Distributions Report\
  6
  7 s/\([0-9]\{2\}\)\/\([0-9]\{2\}\)\/\([0-9]\{4\}\)$/\3-\1-\2/
  8 y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/
  Line 1 of our script is a comment. As in many configuration files and programming languages on Linux systems, comments begin with the # char- acter and are followed by human-readable text. Comments can be placed anywhere in the script (though not within commands themselves) and are helpful to any humans who might need to identify and/or maintain the script.
  Line 2 is a blank line. Like comments, blank lines may be added to improve readability.
  Many sed commands support line addresses. These are used to specify which lines of the input are to be acted upon. Line addresses may be expressed as single line numbers, line-number ranges, and the special line number $, which indicates the last line of input.
  Lines 3 through 6 contain text to be inserted at the address 1, the first line of the input. The i command is followed by the sequence backslash– carriage return to produce an escaped carriage return, or what is called a line-continuation character. This sequence, which can be used in many circum- stances including shell scripts, allows a carriage return to be embedded in
  a stream of text without signaling the interpreter (in this case sed) that the end of the line has been reached. The i command and the commands a (which appends text) and c (which replaces text) allow multiple lines of text, providing that each line, except the last, ends with a line-continuation character. The sixth line of our script is actually the end of our inserted text and ends with a plain carriage return rather than a line-continuation char- acter, signaling the end of the i command.
  Note: A line-continuation character is formed by a backslash followed immediately by a car- riage return. No intermediary spaces are permitted.
  Line 7 is our search-and-replace command. Since it is not preceded by an address, each line in the input stream is subject to its action.
  Line 8 performs transliteration of the lowercase letters into uppercase letters. Note that unlike tr, the y command in sed does not support charac- ter ranges (for example, [a-z]), nor does it support POSIX character classes. Again, since the y command is not preceded by an address, it applies to every line in the input stream.
    262 Chapter 20
  PEOPLE WHO LIKE SED ALSO LIKE...
  sed is a very capable program, able to perform fairly complex editing tasks to streams of text. It is most often used for simple, one-line tasks rather than long scripts. Many users prefer other tools for larger tasks. The most popular of these are awk and perl. These go beyond mere tools like the programs covered here and extend into the realm of complete programming languages. perl, in particular, is often used in place of shell scripts for many system-management and administration tasks, as well as being a very popular medium for web devel- opment. awk is a little more specialized. Its specific strength is its ability to manipu- late tabular data. It resembles sed in that awk programs normally process text files line by line, using a scheme similar to the sed concept of an address fol- lowed by an action. While both awk and perl are outside the scope of this book, they are very good tools for the Linux command line user.

  The Command Line

  They wanted a powerful set of tools that you could mix and match to form powerful composites.

  To that end, they built everything around a simple concept: streams of plain text.

  Virtually all the Unix command- line tools produce and consume plain text.

  Even text files can be converted into a stream of plain text (via the cat command) and put back into a file with the redirection command, the >.
  For a simple example, you can take regular text with the echo command and pipe it through something that converts it from lowercase to uppercase (using the tr, or translate, command). This understands character classes (like :lower: and :upper:) like this (note that the $ isn’t part of the command, the command-line prompt, left there so you can tell input from output):
       $ echo "productively lazy" | tr "[:lower:]" "[:upper:]"
       PRODUCTIVELY LAZY
  The concept worth noticing here is the pipe command (the | character). It takes the output of the echo command and passes it into the tr command, which dutifully translates lowercase characters into uppercase ones. All Unix commands are wired this way, where the output of one becomes the input of the next. You can also create a file with that content by redirecting the output of this command into a file:
       $ echo "productively lazy" | tr "[:lower:]" "[:upper:]" >pl.txt
       $ cat pl.txt
       PRODUCTIVELY LAZY
  And, of course, you can take text from one file, do something to it, and put it into another file:
       $ cat pl.txt | tr "[:upper:]" "[:lower:]" | tr "z" "Z" > plz.txt
       productively laZy
  Here is a more practical example. Suppose I have a large Java project with a bunch of classes that are "helpers" for other classes, and follow a naming convention of Class Helper, for the class it is helping. I want to find them all, even though they are scattered all over my project:
  $ find . -name *Helper.java
  And my army of trained minions dutifully responds:
         ./src/java/org/sample/domain/DomainHelper.java
         ./src/java/org/sample/gui/WindowHelper.java
         ./src/java/org/sample/logic/DocumentHelper.java
         ./src/java/org/sample/logic/GenericHelper.java
  194 APPENDIX: BUILDING BLOCKS
         ./src/java/org/sample/logic/LoginHelper.java
         ./src/java/org/sample/logic/PersistenceHelper.java
  OK, fine, you can get the same result in the search dialog of an IDE. But the interesting thing about the command line is what you can do after you get these results. In an IDE, the results of that search are going to be in a window, and if you are lucky, you might be able to copy them out and paste them someplace. But from the command line, you can pipe that output into another tool. In this case, that tool is wc. wc is a tool that counts things; it can count words, characters, lines, and files:
       $ find . -name *Helper.java | wc -l
       6
  The wc -l line simply counts the number of lines passed into it:
    WHO NAMES THESE THINGS?
  The Unix commands are very terse. After all, they were designed to work on teletype terminals and reward those who learn their way through their terseness. Once you learn them, it takes very little typing to get cool stuff to happen. But what about grep? Where did that come from?
  Rumor has it that the grep command comes to us because of the search command in the ex editor. The ex editor was the line-based precursor to VI, the legendary Unix editor with the steepest imaginable learning curve. In ex, to perform a search, you entered command mode and typed g for global search, started a regular expression with the / character, typed your regular expression, terminated it with another /, and then told ex to print the result with a p. In other words, g/re/p. That was so common amongst Unix types that it became a verb. So, when it came time to write a search utility for the command line, they already had the perfect name: grep.
   I know some of the helpers are actually subclasses of other helpers. I can already use find to find all of the helpers; now I want to look inside those files and find just those that happen to extend other helpers. For that, we use grep. We’ll look at three differently nuanced versions of using the combination of find and grep. The first uses find’s extensive options:
       $ find . -name *Helper.java -exec grep -l "extends .*Helper" {} \;
       ./src/java/org/sample/logic/DocumentHelper.java
       ./src/java/org/sample/logic/LoginHelper.java
  What’s going on in this incantation? See Table A-1 for a breakdown.
  TABLE A-1. Decoding command-line magic
     Character(s)
    What it’s doing
     find
    Execute the find command.
     .
    From the current directory.
     -name
     Matching name of "*Helper.java".
   The Command Line 195
     Character(s)
    What it’s doing
     -exec
    Execute the following command on each found file.
     grep
    grep command.
     -l
     Show the files with matching lines.
     "extends .*Helper"
   Match the regular expression for lines matching "extends" + a single space + zero or more characters + "Helper".
     {}
     The placeholder for the filename found by find.
     \;
    Terminate the command after -exec. Because this is a Unix command, you might want to pipe the results of this into another command, and the find command has to know when the "exec" is done.
   Wow, that’s a lot of bang for the buck in a compact syntax. Which is, of course, the point. Just to prove that many ways exist to do everything on a Unix command line, here is an alternative version that produces the same results, using the xargs command:
       $ find . -name *Helper.java | xargs grep -l "extends .*Helper"
       ./src/java/org/sample/logic/DocumentHelper.java
       ./src/java/org/sample/logic/LoginHelper.java
  Most of this one is the same, except that we’re piping the output of the find command through xargs, which is a helper utility that will take the input from a pipe and place it at the end of its argument. Like the {} placeholder above, xargs will take the filenames produced by the find command and put them as the last parameter of the grep command. You can also use options for the xargs command to put the parameters that come through the pipe at different locations within the argument string. For example, the following command copies all the filenames that start with a capital letter to the dest directory:
       $ ls -1d [A-Z]* | xargs -J % cp -rp % destdir
  The -J flag tells xargs to use the % as the placeholder for the input coming through the pipe. This allows you to specify any replacement character you like, to ensure it doesn’t conflict with some other character required by the target command.
  Here’s one last version of our find command:
       $ grep -l "extends .*Helper" `find . -name *Helper.java`
       ./src/java/org/sample/logic/DocumentHelper.java
       ./src/java/org/sample/logic/LoginHelper.java
  Notice those little backtick characters (`). We aren’t using the pipe to send the output of one command to another—if we did that, grep would simply look through the list of filenames, not the content of the files themselves. Wrapping the find command in the backtick character (typically found at the upper left of U.S. keyboards) will make find execute first, and pass the output to grep as the list of files to search instead of the actual text to search.
  Now, I glue together all of the stuff seen so far:
  196
  $ grep -l "extends .*Helper" `find . -name *Helper.java` | wc -l
  2
  APPENDIX: BUILDING BLOCKS
  While the individual commands were pretty trivial, with the pipe and the backtick, I can combine them in ways their original authors might not have anticipated (and that is a major philosophical point behind Unix). With the knowledge of a dozen commands or so, you too can look like a Unix power user. More importantly, you can slice and dice your projects in ways that just are not available from the menus inside of IDEs.

### VO 600w
  *sed

  Substitute on all lines (all occurrences):

      s/xx/yy/g

  Delete lines containing BSD :

      /BSD/d

  Print the lines between each pair of BEGIN and END , inclusive:

      /^BEGIN/,/^END/p

  Delete any line that doesn't contain SAVE :

      /SAVE/!d

  Substitute on all lines, except between BEGIN and END :

      /BEGIN/,/END/!s/xx/yy/g

  Example

      # Replace first 100 lines in a file:
      1,100c\

      ...first replacement line
      \

      ...second replacement line
      \

      ...
      \

      ...last replacement line

  d

      [ address1 ][, address2 ]d

      Delete the addressed line (or lines) from the pattern space. Thus, the line is not passed to standard output. A new line of input is read, and editing resumes with the first command in the script. See articles 34.4 and 34.18 .

      Example

          # delete all blank lines:
          /^$/d

  i

          [ address ]i\
          text

      Insert text before each line matched by address . (See a for details on text .) Article 43.20 shows a script that uses i .

      Example

          /Item 1/i\
          The five items are listed below:

  s

      [ address1 ][ , address2 ] s/ pattern / replacement / [ flags ]

      Substitute replacement for pattern on each addressed line. If pattern addresses are used, the pattern // represents the last pattern address specified. The following flags can be specified:

    g

        Replace all instances of / pattern / on each addressed line, not just the first instance.

  *tr

  tr "[:lower:]" "[:upper:]" < file1
  For example:
  $ tr "[:lower:]" "[:upper:]" < todo 1. WAKE UP
  2. LOOK IN MIRROR
  3. SIGH
      4. GO BACK TO BED.
      $
  The tr command has a number of different options for power users, including -c to invert the specified pattern (that is, if you specify tr -c "abc", the program matches anything other than a, b, or c), and -d deletes any characters from the first pattern specified.
  To remove all vowels from the input, you could use:
  $ tr -d "[aeiou]" < todo 1. Wk p

  *cut

  The cut program is used to extract a section of text from a line and output the extracted section to standard output. It can accept multiple file argu- ments or input from standard input.
  Specifying the section of the line to be extracted is somewhat awkward and is specified using the options shown in Table 20-3.

  Option
  -c char_list
  -f field_list
  -d delim_char
  --complement
  Description
  Extract the portion of the line defined by char_list. The list may consist of one or more comma-separated numerical ranges.
  Extract one or more fields from the line as defined by field_list. The list may contain one or more fields or field ranges separated by commas.
  When -f is specified, use delim_char as the field delimit- ing character. By default, fields must be separated by a single tab character.
  Extract the entire line of text, except for those portions specified by -c and/or -f.

  *sort

  $ ls -l | sort -nk 5 | less
   -b         --ignore-leading-blanks
  -f --ignore-case -n --numeric-sort
  -r --reverse
  -k --key=field1[,field2]
  -m --merge
  -o --output=file
  -t --field-separator=cha

  *uniq

  Compared to sort, the uniq program is a lightweight. uniq performs a seem- ingly trivial task. When given a sorted file (including standard input), it removes any duplicate lines and sends the results to standard output. It is often used in conjunction with sort to clean the output of duplicates.

  Note: While uniq is a traditional Unix tool often used with sort, the GNU version of sort supports a -u option, which removes duplicates from the sorted output.

  -c -d
  -f n
  -i -s n -u
  Description
  Output a list of duplicate lines preceded by the number of times the line occurs.
  Output only repeated lines, rather than unique lines.
  Ignore n leading fields in each line. Fields are separated by whitespace as they are in sort; however, unlike sort, uniq has no option for setting an alternative field separator.
  Ignore case during the line comparisons.
  Skip (ignore) the leading n characters of each line. Output only unique lines. This is the default.
              Here we see uniq used to report the number of duplicates found in our text file, using the -c option:
  [me@linuxbox ~]$ sort foo.txt | uniq -c 2a

  *wc

  $ find . -name *.rb | wc -l

## Networking 2m

  NETWORKING

  When it comes to networking, there is probably noth- ing that cannot be done with Linux. Linux is used to build all sorts of networking systems and appli- ances, including firewalls, routers, name servers, NAS (network-attached storage) boxes, and on and on.
  Just as the subject of networking is vast, so is the number of commands that can be used to configure and control it. We will focus our attention on just a few of the most frequently used ones. The commands chosen for exam- ination include those used to monitor networks and those used to transfer files. In addition, we are going to explore the ssh program, which is used to perform remote logins. This chapter will cover the following:
    ping—Send an ICMP ECHO_REQUEST to network hosts.
    traceroute—Print the route packets trace to a network host.
    netstat—Print network connections, routing tables, interface statis- tics, masquerade connections, and multicast memberships.
    ftp—Internet file transfer program.
    lftp—An improved Internet file transfer program.
    wget—Non-interactive network downloader.
    ssh—OpenSSH SSH client (remote login program).
    scp—Secure copy (remote file copy program).
    sftp—Secure file transfer program.
  We’re going to assume a little background in networking. In this, the Internet age, everyone using a computer needs a basic understanding of networking concepts. To make full use of this chapter, you should be famil- iar with the following terms:
    IP (Internet protocol) address
    Host and domain name
    URI (uniform resource identifier)
  Note: Some of the commands we will cover may (depending on your distribution) require the installation of additional packages from your distribution’s repositories, and some may require superuser privileges to execute.
  Examining and Monitoring a Network
  Even if you’re not the system administrator, it’s often helpful to examine the performance and operation of a network.
  ping—Send a Special Packet to a Network Host
  The most basic network command is ping. The ping command sends a spe- cial network packet called an IMCP ECHO_REQUEST to a specified host. Most network devices receiving this packet will reply to it, allowing the net- work connection to be verified.
  Note: It is possible to configure most network devices (including Linux hosts) to ignore these packets. This is usually done for security reasons, to partially obscure a host from a potential attacker. It is also common for firewalls to be configured to block IMCP traffic.
  For example, to see if we can reach http://www.linuxcommand.org/ (one of my favorite sites ;-)), we can use ping like this:
  [me@linuxbox ~]$ ping linuxcommand.org
  Once started, ping continues to send packets at a specified interval
  (default is 1 second) until it is interrupted:
  [me@linuxbox ~]$ ping linuxcommand.org
  PING linuxcommand.org (66.35.250.210) 56(84) bytes of data.
     176
  Chapter 16
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=1 ttl=43 time=10 7 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=2 ttl=43 time=10 8 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=3 ttl=43 time=10 6 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=4 ttl=43 time=10 6 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=5 ttl=43 time=10 5 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=6 ttl=43 time=10 7 ms
  --- linuxcommand.org ping statistics ---
  6 packets transmitted, 6 received, 0% packet loss, time 6010ms rtt min/avg/max/mdev = 105.647/107.052/108.118/0.824 ms
  After it is interrupted (in this case after the sixth packet) by the pressing of CTRL-C, ping prints performance statistics. A properly performing network will exhibit zero percent packet loss. A successful ping will indicate that the elements of the network (its interface cards, cabling, routing, and gateways) are in generally good working order.
  traceroute—Trace the Path of a Network Packet
  The traceroute program (some systems use the similar tracepath program instead) displays a listing of all the "hops" network traffic takes to get from the local system to a specified host. For example, to see the route taken to reach http://www.slashdot.org/, we would do this:
  [me@linuxbox ~]$ traceroute slashdot.org The output looks like this:
  traceroute to slashdot.org (216.34.181.45), 30 hops max, 40 byte packets 1 ipcop.localdomain (192.168.1.1) 1.066 ms 1.366 ms 1.720 ms
  2 * **
  3 ge-4-13-ur01.rockville.md.bad.comcast.net (68.87.130.9) 14.622 ms 14.885
  ms 15.169 ms
  4 po-30-ur02.rockville.md.bad.comcast.net (68.87.129.154) 17.634 ms 17.626
  ms 17.899 ms
  5 po-60-ur03.rockville.md.bad.comcast.net (68.87.129.158) 15.992 ms 15.983
  ms 16.256 ms
  6 po-30-ar01.howardcounty.md.bad.comcast.net (68.87.136.5) 22.835 ms 14.23
  3 ms 14.405 ms
  7 po-10-ar02.whitemarsh.md.bad.comcast.net (68.87.129.34) 16.154 ms 13.600
  ms 18.867 ms
  8 te-0-3-0-1-cr01.philadelphia.pa.ibone.comcast.net (68.86.90.77) 21.951 ms
  21.073 ms 21.557 ms
  9 pos-0-8-0-0-cr01.newyork.ny.ibone.comcast.net (68.86.85.10) 22.917 ms 21
  .884 ms 22.126 ms
  10 204.70.144.1 (204.70.144.1) 43.110 ms 21.248 ms 21.264 ms
  11 cr1-pos-0-7-3-1.newyork.savvis.net (204.70.195.93) 21.857 ms cr2-pos-0-0- 3-1.newyork.savvis.net (204.70.204.238) 19.556 ms cr1-pos-0-7-3-1.newyork.sav vis.net (204.70.195.93) 19.634 ms
      Networking 177
  12 cr2-pos-0-7-3-0.chicago.savvis.net (204.70.192.109) 41.586 ms 42.843 ms cr2-tengig-0-0-2-0.chicago.savvis.net (204.70.196.242) 43.115 ms
  13 hr2-tengigabitethernet-12-1.elkgrovech3.savvis.net (204.70.195.122) 44.21 5 ms 41.833 ms 45.658 ms
  14 csr1-ve241.elkgrovech3.savvis.net (216.64.194.42) 46.840 ms 43.372 ms 4 7.041 ms
  15 64.27.160.194 (64.27.160.194) 56.137 ms 55.887 ms 52.810 ms
  16 slashdot.org (216.34.181.45) 42.727 ms 42.016 ms 41.437 ms
  In the output, we can see that connecting from our test system to http:// www.slashdot.org/ requires traversing 16 routers. For routers that provide identifying information, we see their hostnames, IP addresses, and perform- ance data, which include three samples of round-trip time from the local system to the router. For routers that do not provide identifying information (because of router configuration, network congestion, firewalls, etc.), we see asterisks as in the line for hop number two.
  netstat—Examine Network Settings and Statistics
  The netstat program is used to examine various network settings and statis- tics. Through the use of its many options, we can look at a variety of features in our network setup. Using the -ie option, we can examine the network interfaces in our system:
  [me@linuxbox ~]$ netstat -ie
  eth0 Link encap:Ethernet HWaddr 00:1d:09:9b:99:67
  inet addr:192.168.1.2 Bcast:192.168.1.255 Mask:255.255.255.0 inet6 addr: fe80::21d:9ff:fe9b:9967/64 Scope:Link
  UP BROADCAST RUNNING MULTICAST MTU:1500 Metric:1
  RX packets:238488 errors:0 dropped:0 overruns:0 frame:0
          TX packets:403217 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:100
          RX bytes:153098921 (146.0 MB)  TX bytes:261035246 (248.9 MB)
          Memory:fdfc0000-fdfe0000
  lo Link encap:Local Loopback
  inet addr:127.0.0.1 Mask:255.0.0.0
  inet6 addr: ::1/128 Scope:Host
  UP LOOPBACK RUNNING MTU:16436 Metric:1
  RX packets:2208 errors:0 dropped:0 overruns:0 frame:0 TX packets:2208 errors:0 dropped:0 overruns:0 carrier:0 collisions:0 txqueuelen:0
  RX bytes:111490 (108.8 KB) TX bytes:111490 (108.8 KB)
  In the example above, we see that our test system has two network inter- faces. The first, called eth0, is the Ethernet interface; the second, called lo, is the loopback interface, a virtual interface that the system uses to "talk to itself."
  When performing causal network diagnostics, the important things to look for are the presence of the word UP at the beginning of the fourth line for each interface, indicating that the network interface is enabled, and the presence of a valid IP address in the inet addr field on the second line. For systems using Dynamic Host Configuration Protocol (DHCP), a valid IP address in this field will verify that the DHCP is working.
     178 Chapter 16
  Using the -r option will display the kernel’s network routing table. This shows how the network is configured to send packets from network to network:
  [me@linuxbox ~]$ netstat -r
   Kernel IP routing table
  Destination  Gateway
  192.168.1.0  *
  192.168.1.1 0.0.0.0
  Genmask       Flags   MSS Window  irtt Iface
  255.255.255.0 U         0 0          0 eth0  default
  UG 0 0 0 eth0
   In this simple example, we see a typical routing table for a client machine on a local area network (LAN) behind a firewall/router. The first line of the listing shows the destination 192.168.1.0. IP addresses that end in zero refer to networks rather than individual hosts, so this destination means any host on the LAN. The next field, Gateway, is the name or IP address of the gateway (router) used to go from the current host to the destination network. An asterisk in this field indicates that no gateway is needed.
  The last line contains the destination default. This means any traffic destined for a network that is not otherwise listed in the table. In our example, we see that the gateway is defined as a router with the address of 192.168.1.1, which presumably knows what to do with the destination traffic.
  The netstat program has many options, and we have looked at only a couple. Check out the netstat man page for a complete list.
  Transporting Files over a Network
  What good is a network unless we know how to move files across it? There are many programs that move data over networks. We will cover two of them now and several more in later sections.
  ftp—Transfer Files with the File Transfer Protocol
  One of the true "classic" programs, ftp gets its name from the protocol it uses, the File Transfer Protocol. FTP is used widely on the Internet for file downloads. Most, if not all, web browsers support it, and you often see URIs starting with the protocol ftp://.
  Before there were web browsers, there was the ftp program. ftp is used to communicate with FTP servers, machines that contain files that can be uploaded and downloaded over a network.
  FTP (in its original form) is not secure, because it sends account names and passwords in cleartext. This means that they are not encrypted and any- one sniffing the network can see them. Because of this, almost all FTP done over the Internet is done by anonymous FTP servers. An anonymous server allows anyone to log in using the login name anonymous and a meaningless password.
  In the following example, we show a typical session with the ftp pro- gram downloading an Ubuntu ISO image located in the /pub/cd_images/ Ubuntu-8.04 directory of the anonymous FTP server fileserver.
  Networking 179
  [me@linuxbox ~]$ ftp fileserver
  Connected to fileserver.localdomain.
  220 (vsFTPd 2.0.1)
  Name (fileserver:me): anonymous
  331 Please specify the password.
  Password:
  230 Login successful.
  Remote system type is UNIX.
  Using binary mode to transfer files.
  ftp> cd pub/cd_images/Ubuntu-8.04
  250 Directory successfully changed.
  ftp> ls
  200 PORT command successful. Consider using PASV.
  150 Here comes the directory listing.
  -rw-rw-r-- 1 500 500 733079552 Apr 25 03:53 ubuntu-8.04-desktop- i386.iso
  226 Directory send OK.
  ftp> lcd Desktop
  Local directory now /home/me/Desktop
  ftp> get ubuntu-8.04-desktop-i386.iso
  local: ubuntu-8.04-desktop-i386.iso remote: ubuntu-8.04-desktop-i386.iso
  200 PORT command successful. Consider using PASV.
  150 Opening BINARY mode data connection for ubuntu-8.04-desktop-i386.iso (733079552 bytes).
  226 File send OK.
  733079552 bytes received in 68.56 secs (10441.5 kB/s)
  ftp> bye
  Table 16-1 gives an explanation of the commands entered during this session.
  Table 16-1: Examples of Interactive ftp Commands
    Command
  ftp fileserver
  anonymous
  cd pub/cd_images/Ubuntu-8.04
  ls
  Meaning
  Invoke the ftp program and have it connect to the FTP server fileserver.
  Login name. After the login prompt, a password prompt will appear. Some servers will accept a blank password. Others will require a password in the form of an email address. In that case, try something like user@example.com.
  Change to the directory on the remote system containing the desired file. Note that on most anonymous FTP servers, the files for public downloading are found somewhere under the pub directory.
  List the directory on the remote system.
          180 Chapter 16
  Table 16-1 (continued) Command
  lcd Desktop
   get ubuntu-8.04-desktop-i386.iso
  bye
  Meaning
  Change the directory on the local system to ~/Desktop. In the example, the ftp program was invoked when the working directory was ~. This command changes the working directory to ~/Desktop.
  Tell the remote system to transfer the file ubuntu-8.04-desktop-i386.iso to the local system. Since the working directory on the local system was changed to ~/Desktop, the file will be downloaded there.
  Log off the remote server and end the ftp program session. The commands quit and exit may also be used.
         Typing help at the ftp> prompt will display a list of the supported com- mands. Using ftp on a server where sufficient permissions have been granted, it is possible to perform many ordinary file management tasks. It’s clumsy, but it does work.
  lftp—A Better ftp
  ftp is not the only command-line FTP client. In fact, there are many. One of the better (and more popular) ones is lftp by Alexander Lukyanov. It works much like the traditional ftp program but has many additional convenience features, including multiple-protocol support (including HTTP), automatic retry on failed downloads, background processes, tab completion of path- names, and many more.
  wget—Non-interactive Network Downloader
  Another popular command-line program for file downloading is wget. It is useful for downloading content from both web and FTP sites. Single files, multiple files, and even entire sites can be downloaded. To download the first page of http://www.linuxcommand.org/, we could do this:
  [me@linuxbox ~]$ wget http://linuxcommand.org/index.php --11:02:51-- http://linuxcommand.org/index.php
             => `index.php'
  Resolving linuxcommand.org... 66.35.250.210
  Connecting to linuxcommand.org|66.35.250.210|:80... connected.
   Networking 181
  HTTP request sent, awaiting response... 200 OK Length: unspecified [text/html]
                   [ <=>                                 ] 3,120         --.--K/s
               11:02:51 (161.75 MB/s) - `index.php' saved [3120]
  The program’s many options allow wget to recursively download, down- load files in the background (allowing you to log off but continue down- loading), and complete the download of a partially downloaded file. These features are well documented in its better-than-average man page.
  Secure Communication with Remote Hosts
  For many years, Unix-like operating systems have had the ability to be administered remotely via a network. In the early days, before the general adoption of the Internet, there were a couple of popular programs used to log in to remote hosts: the rlogin and telnet programs. These programs, however, suffer from the same fatal flaw that the ftp program does; they transmit all their communications (including login names and passwords) in cleartext. This makes them wholly inappropriate for use in the Internet age.
  ssh—Securely Log in to Remote Computers
  To address this problem, a new protocol called SSH (Secure Shell) was developed. SSH solves the two basic problems of secure communication with a remote host. First, it authenticates that the remote host is who it says it is (thus preventing man-in-the-middle attacks), and second, it encrypts all of the communications between the local and remote hosts.
  SSH consists of two parts. An SSH server runs on the remote host, listen- ing for incoming connections on port 22, while an SSH client is used on the local system to communicate with the remote server.
  Most Linux distributions ship an implementation of SSH called OpenSSH from the BSD project. Some distributions include both the client and the server packages by default (for example, Red Hat), while others (such as Ubuntu) supply only the client. To enable a system to receive remote con- nections, it must have the OpenSSH-server package installed, configured, and running, and (if the system is either running or behind a firewall) it must allow incoming network connections on TCP port 22.
  Note: If you don’t have a remote system to connect to but want to try these examples, make sure the OpenSSH-server package is installed on your system and use localhost as the name of the remote host. That way, your machine will create network connections with itself.
   182
  Chapter 16
  The SSH client program used to connect to remote SSH servers is called, appropriately enough, ssh. To connect to a remote host named remote-sys, we would use the ssh client program like so:
  [me@linuxbox ~]$ ssh remote-sys
  The authenticity of host 'remote-sys (192.168.1.4)' can't be established. RSA key fingerprint is 41:ed:7a:df:23:19:bf:3c:a5:17:bc:61:b3:7f:d9:bb. Are you sure you want to continue connecting (yes/no)?
  The first time the connection is attempted, a message is displayed indi- cating that the authenticity of the remote host cannot be established. This is because the client program has never seen this remote host before. To accept the credentials of the remote host, enter yes when prompted. Once the connection is established, the user is prompted for a password:
  Warning: Permanently added 'remote-sys,192.168.1.4' (RSA) to the list of known hosts.
  me@remote-sys's password:
  After the password is successfully entered, we receive the shell prompt from the remote system:
  Last login: Tue Aug 30 13:00:48 2011
  [me@remote-sys ~]$
  The remote shell session continues until the user enters the exit com- mand at the remote shell prompt, thereby closing the remote connection. At this point, the local shell session resumes, and the local shell prompt reappears.
  It is also possible to connect to remote systems using a different user- name. For example, if the local user me had an account named bob on a remote system, user me could log in to the account bob on the remote system as follows:
  [me@linuxbox ~]$ ssh bob@remote-sys bob@remote-sys's password:
  Last login: Tue Aug 30 13:03:21 2011 [bob@remote-sys ~]$
  As stated before, ssh verifies the authenticity of the remote host. If the remote host does not successfully authenticate, the following message appears:
  [me@linuxbox ~]$ ssh remote-sys @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
  @ WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! @ @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
  IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
  Someone could be eavesdropping on you right now (man-in-the-middle attack)! It is also possible that the RSA host key has just been changed.
           Networking 183
  The fingerprint for the RSA key sent by the remote host is 41:ed:7a:df:23:19:bf:3c:a5:17:bc:61:b3:7f:d9:bb.
  Please contact your system administrator.
  Add correct host key in /home/me/.ssh/known_hosts to get rid of this message. Offending key in /home/me/.ssh/known_hosts:1
  RSA host key for remote-sys has changed and you have requested strict checking.
  Host key verification failed.
  This message is caused by one of two possible situations. First, an attacker may be attempting a man-in-the-middle attack. This is rare, because every- body knows that ssh alerts the user to this. The more likely culprit is that the remote system has been changed somehow; for example, its operating system or SSH server has been reinstalled. In the interests of security and safety, however, the first possibility should not be dismissed out of hand. Always check with the administrator of the remote system when this message occurs.
  After determining that the message is due to a benign cause, it is safe to correct the problem on the client side. This is done by using a text editor (vim perhaps) to remove the obsolete key from the ~/.ssh/known_hosts file. In the example message above, we see this:
  Offending key in /home/me/.ssh/known_hosts:1
  This means that line 1 of the known_hosts file contains the offending key. Delete this line from the file, and the ssh program will be able to accept new authentication credentials from the remote system.
  Besides opening a shell session on a remote system, ssh also allows us to execute a single command on a remote system. For example, we can execute the free command on a remote host named remote-sys and have the results displayed on the local system:
      [me@linuxbox ~]$ ssh remote-sys free
  me@twin4's password:
               total
  shared    buffers     cached
       0     110068     154596
                         used     free
                       507184   268352
                       242520   533016
  It’s possible to use this technique in more interesting ways, such as this example in which we perform an ls on the remote system and redirect the output to a file on the local system:
  [me@linuxbox ~]$ ssh remote-sys 'ls *' > dirlist.txt me@twin4's password:
  [me@linuxbox ~]$
  Notice the use of the single quotes. This is done because we do not want the pathname expansion performed on the local machine; rather, we want it to be performed on the remote system. Likewise, if we had wanted the output
  Mem:        775536
  -/+ buffers/cache:
  Swap:      1572856        0    1572856
  [me@linuxbox ~]$
     184 Chapter 16
  redirected to a file on the remote machine, we could have placed the redir- ection operator and the filename within the single quotes:
  [me@linuxbox ~]$ ssh remote-sys 'ls * > dirlist.txt'
        TUNNELING WITH SSH
  Part of what happens when you establish a connection with a remote host via SSH is that an encrypted tunnel is created between the local and remote systems. Normally, this tunnel is used to allow commands typed at the local system to be transmitted safely to the remote system and the results to be transmitted safely back. In addition to this basic function, the SSH protocol allows most types of network traffic to be sent through the encrypted tunnel, creating a sort of VPN (virtual private network) between the local and remote systems.
  Perhaps the most common use of this feature is to allow X Window system traffic to be transmitted. On a system running an X server (that is, a machine displaying a GUI), it is possible to launch and run an X client program (a graph- ical application) on a remote system and have its display appear on the local system. It’s easy to do—here’s an example. Let’s say we are sitting at a Linux sys- tem called linuxbox that is running an X server, and we want to run the xload program on a remote system named remote-sys and see the program’s graphical output on our local system. We could do this:
       [me@linuxbox ~]$ ssh -X remote-sys me@remote-sys's password:
  Last login: Mon Sep 05 13:23:11 2011 [me@remote-sys ~]$ xload
     After the xload command is executed on the remote system, its window appears on the local system. On some systems, you may need to use the -Y option rather than the -X option to do this.
   scp and sftp—Securely Transfer Files
  The OpenSSH package also includes two programs that can make use of an SSH- encrypted tunnel to copy files across the network. The first, scp (secure copy) is used much like the familiar cp program to copy files. The most notable difference is that the source or destination pathname may be preceded with the name of a remote host followed by a colon character. For example, if we wanted to copy a document named document.txt from our home directory on the remote system, remote-sys, to the current working directory on our local system, we could do this:
  [me@linuxbox ~]$ scp remote-sys:document.txt .
  me@remote-sys's password:
  document.txt 100% 5581 5.5KB/s 00:00 [me@linuxbox ~]$
    Networking 185
  As with ssh, you may apply a username to the beginning of the remote host’s name if the desired remote host account name does not match that of the local system:
  [me@linuxbox ~]$ scp bob@remote-sys:document.txt .
  The second SSH file-copying program is sftp, which, as its name implies, is a secure replacement for the ftp program. sftp works much like the ori- ginal ftp program that we used earlier; however, instead of transmitting everything in cleartext, it uses an SSH-encrypted tunnel. sftp has an impor- tant advantage over conventional ftp in that it does not require an FTP server to be running on the remote host. It requires only the SSH server. This means that any remote machine that can connect with the SSH client can also be used as a FTP-like server. Here is a sample session:
  [me@linuxbox ~]$ sftp remote-sys Connecting to remote-sys... me@remote-sys's password:
  sftp> ls ubuntu-8.04-desktop-i386.iso sftp> lcd Desktop
  sftp> get ubuntu-8.04-desktop-i386.iso
  Fetching /home/me/ubuntu-8.04-desktop-i386.iso to ubuntu-8.04-desktop-i386.iso
  /home/me/ubuntu-8.04-desktop-i386.iso 100% 699MB 7.4MB/s 01:35 sftp> bye
  Note: The SFTP protocol is supported by many of the graphical file managers found in Linux distributions. Using either Nautilus (GNOME) or Konqueror (KDE), we can enter a URI beginning with sftp:// into the location bar and operate on files stored on a remote system running an SSH server.

### VO 300w

  $ nmap
  $ lsof

  ping—Send an ICMP ECHO_REQUEST to network hosts.
  traceroute—Print the route packets trace to a network host.


  $ ping google.com
  $ traceroute google.com
  (xtraceroute ?)

  ftp—Internet file transfer program.

  ftp archive.org

  wget—Non-interactive network downloader.

  $ wget -r $RAILS_GUIDES

  open `find guides.rubyonrails.org -iname "*active_record*"`

  ssh—OpenSSH SSH client (remote login program).

  keys

  As stated before, ssh verifies the authenticity of the remote host.

  If the remote host does not successfully authenticate, the following message appears:

  @ WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! @

  Add correct host key in /home/me/.ssh/known_hosts to get rid of this message.

  Offending key in /home/me/.ssh/known_hosts:1
  RSA host key for remote-sys has changed and you have requested strict checking.

  This message is caused by one of two possible situations. First, an attacker may be attempting a man-in-the-middle attack. This is rare, because every- body knows that ssh alerts the user to this.

  The more likely culprit is that the remote system has been changed somehow; for example, its operating system or SSH server has been reinstalled. In the interests of security and safety, however, the first possibility should not be dismissed out of hand.

  Always check with the administrator of the remote system when this message occurs.

  After determining that the message is due to a benign cause, it is safe to correct the problem on the client side.

  This is done by using a text editor (vim perhaps) to remove the obsolete key from the ~/.ssh/known_hosts file. In the example message above, we see this:

  Offending key in /home/me/.ssh/known_hosts:1

  This means that line 1 of the known_hosts file contains the offending key.

  Delete this line from the file, and the ssh program will be able to accept new authentication credentials from the remote system.

  Besides opening a shell session on a remote system, ssh also allows us to execute a single command on a remote system.

  For example, we can execute the free command on a remote host named remote-sys and have the results displayed on the local system:

  [me@linuxbox ~]$ ssh remote-sys free

  It’s possible to use this technique in more interesting ways, such as this example in which we perform an ls on the remote system and redirect the output to a file on the local system:

  [me@linuxbox ~]$ ssh remote-sys 'ls *' > dirlist.txt me@twin4's password:
  [me@linuxbox ~]$

  Notice the use of the single quotes. This is done because we do not want the pathname expansion performed on the local machine; rather, we want it to be performed on the remote system. Likewise, if we had wanted the output
  Mem:        775536
  -/+ buffers/cache:
  Swap:      1572856        0    1572856
  [me@linuxbox ~]$

  redirected to a file on the remote machine, we could have placed the redir- ection operator and the filename within the single quotes:
  [me@linuxbox ~]$ ssh remote-sys 'ls * > dirlist.txt'

  scp and sftp—Securely Transfer Files

  [me@linuxbox ~]$ scp remote-sys:document.txt .
  me@remote-sys's password:
  document.txt 100% 5581 5.5KB/s 00:00 [me@linuxbox ~]$

  [me@linuxbox ~]$ scp bob@remote-sys:document.txt .

## Processes 4m

  PROCESSES
  Modern operating systems are usually multitasking, meaning that they create the illusion of doing more than one thing at once by rapidly switching from one executing program to another. The Linux kernel manages this through the use of processes. Processes are how Linux organizes the different programs wait- ing for their turn at the CPU.
  Sometimes a computer will become sluggish, or an application will stop responding. In this chapter, we will look at some of the tools available at the command line that let us examine what programs are doing and how to ter- minate processes that are misbehaving.
  This chapter will introduce the following commands:
    ps—Report a snapshot of current processes.
    top—Display tasks.
    jobs—List active jobs.
    bg—Place a job in the background.
    fg—Place a job in the foreground.
    kill—Send a signal to a process.
    killall—Kill processes by name.
    shutdown—Shut down or reboot the system. How a Process Works
  When a system starts up, the kernel initiates a few of its own activities as pro- cesses and launches a program called init. init, in turn, runs a series of shell scripts (located in /etc) called init scripts, which start all the system services. Many of these services are implemented as daemon programs, programs that just sit in the background and do their thing without having any user inter- face. So even if we are not logged in, the system is at least a little busy per- forming routine stuff.
  The fact that a program can launch other programs is expressed in the process scheme as a parent process producing a child process.
  The kernel maintains information about each process to help keep things organized. For example, each process is assigned a number called a process ID (PID). PIDs are assigned in ascending order, with init always get- ting PID 1. The kernel also keeps track of the memory assigned to each pro- cess, as well as the processes’ readiness to resume execution. Like files, processes also have owners and user IDs, effective user IDs, and so on.
  Viewing Processes with ps
  The most commonly used command to view processes (there are several) is ps. The ps program has a lot of options, but in it simplest form it is used like this:
  [me@linuxbox ~]$ ps
     PID TTY
   5198 pts/1
  10129 pts/1
      TIME CMD
  00:00:00 bash
  00:00:00 ps
   96 Chapter 10
  The result in this example lists two processes: process 5198 and pro- cess 10129, which are bash and ps respectively. As we can see, by default ps doesn’t show us very much, just the processes associated with the current terminal session. To see more, we need to add some options, but before we do that, let’s look at the other fields produced by ps. TTY is short for teletype and refers to the controlling terminal for the process. Unix is showing its age here. The TIME field is the amount of CPU time consumed by the process. As we can see, neither process makes the computer work very hard.
  If we add an option, we can get a bigger picture of what the system is doing:
  [me@linuxbox ~]$ ps x
     PID TTY
   2799 ?
   2820 ?
  15647 ?
  15751 ?
  15754 ?
  15755 ?
  15774 ?
  15793 ?
  15794 ?
  15797 ?
  STAT   TIME COMMAND
  Ssl    0:00 /usr/libexec/bonobo-activation-server –ac
  Sl     0:01 /usr/libexec/evolution-data-server-1.10 --
  Ss     0:00 /bin/sh /usr/bin/startkde
  Ss     0:00 /usr/bin/ssh-agent /usr/bin/dbus-launch --
  S      0:00 /usr/bin/dbus-launch --exit-with-session
  Ss     0:01 /bin/dbus-daemon --fork --print-pid 4 –pr
  Ss     0:02 /usr/bin/gpg-agent -s –daemon
  S      0:00 start_kdeinit --new-startup +kcminit_start
  Ss     0:00 kdeinit Running...
  S      0:00 dcopserver –nosid
  and many more...
  Adding the x option (note that there is no leading dash) tells ps to show all of our processes regardless of what terminal (if any) they are controlled by. The presence of a ? in the TTY column indicates no controlling terminal. Using this option, we see a list of every process that we own.
  Since the system is running a lot of processes, ps produces a long list. It is often helpful to pipe the output from ps into less for easier viewing. Some option combinations also produce long lines of output, so maximizing the terminal emulator window may be a good idea, too.
  A new column titled STAT has been added to the output. STAT is short for state and reveals the current status of the process, as shown in Table 10-1.
  Table 10-1: Process States
  State Meaning
  R Running. The process is running or ready to run.
  S Sleeping. The process is not running; rather, it is waiting for an event,
  such as a keystroke or network packet.
  D Uninterruptible sleep. Process is waiting for I/O such as a disk drive.
  T Stopped. Process has been instructed to stop (more on this later).
  Z A defunct or "zombie" process. This is a child process that has terminated but has not been cleaned up by its parent.
  < A high-priority process. It’s possible to grant more importance to a process, giving it more time on the CPU. This property of a process is called niceness. A process with high priority is said to be less nice because it’s taking more of the CPU’s time, which leaves less for everybody else.
  N A low-priority process. A process with low priority (a nice process) will get processor time only after other processes with higher priority have been serviced.
                  Processes 97
  The process state may be followed by other characters. These indicate various exotic process characteristics. See the ps man page for more detail.
  Another popular set of options is aux (without a leading dash). This gives us even more information:
   [me@linuxbox ~]$ ps aux
  USER PID %CPU %MEM VSZ RSS TTY root 1 0.0 0.0 2136 644 ?
  STAT START   TIME COMMAND
  Ss   Mar05   0:31 init
  root      2  0.0  0.0
  root      3  0.0  0.0
  root      4  0.0  0.0
  root      5  0.0  0.0
  root      6  0.0  0.0
  root      7  0.0  0.0
  and many more...
  0 0? 0 0? 0 0? 0 0? 0 0? 0 0?
  S   Mar05
  S   Mar05
  S   Mar05
  S   Mar05
  S   Mar05
  S   Mar05
  0:00 [kt]
  0:00 [mi]
  0:00 [ks]
  0:06 [wa]
  0:36 [ev]
  0:00 [kh]
   This set of options displays the processes belonging to every user. Using the options without the leading dash invokes the command with "BSD-style" behavior. The Linux version of ps can emulate the behavior of the ps pro- gram found in several Unix implementations. With these options, we get the additional columns shown in Table 10-2.
  Table 10-2: BSD-Style ps Column Headers
  Header Meaning
  USER User ID. This is the owner of the process. %CPU CPU usage as a percent.
  %MEM Memory usage as a percent.
  VSZ Virtual memory size.
  RSS Resident Set Size. The amount of physical memory (RAM) the process is using in kilobytes.
  START Time when the process started. For values over 24 hours, a date is used.
  Viewing Processes Dynamically with top
  While the ps command can reveal a lot about what the machine is doing, it provides only a snapshot of the machine’s state at the moment the ps com- mand is executed. To see a more dynamic view of the machine’s activity, we use the top command:
  [me@linuxbox ~]$ top
  The top program displays a continuously updating (by default, every
  3 seconds) display of the system processes listed in order of process activity.
                 98 Chapter 10
  Its name comes from the fact that the top program is used to see the "top" processes on the system. The top display consists of two parts: a system sum- mary at the top of the display, followed by a table of processes sorted by CPU activity:
  top - 14:59:20 up 6:30, 2 users, load average: 0.07, 0.02, 0.00 Tasks: 109 total, 1 running, 106 sleeping, 0 stopped, 2 zombie Cpu(s): 0.7%us, 1.0%sy, 0.0%ni, 98.3%id, 0.0%wa, 0.0%hi, 0.0%si
   Mem:    319496k total,   314860k used,
  Swap:   875500k total,   149128k used,
    4636k free,    19392k buff
  726372k free,   114676k cach
  PID USER
   6244 me
  11071 me
   6180 me
   6321 me
   4955 root
      1 root
  PR  NI  VIRT  RES  SHR
  39 19 31752 3124 2188 20 0 2304 1092 840 20 0 2700 1100 772 20 0 20944 7248 6560 20 0 104m 9668 5776 20 0 2976 528 476
  S %CPU %MEM
  S  6.3  1.0
  R  1.3  0.3
  S  0.7  0.3
  S  0.7  2.3
  S  0.3  3.0
  S  0.0  0.2
    TIME+  COMMAND
  16:24.42 trackerd
   0:00.14 top
   0:03.66 dbus-dae
   2:51.38 multiloa
   2:19.39 Xorg
   0:03.14 init
       2 root      15  -5     0    0    0 S  0.0  0.0   0:00.00 kthreadd
      3 root      RT  -5     0    0    0 S  0.0  0.0   0:00.00 migratio
      4 root      15  -5     0    0    0 S  0.0  0.0   0:00.72 ksoftirq
      5 root      RT  -5     0    0    0 S  0.0  0.0   0:00.04 watchdog
      6 root      15  -5     0    0    0 S  0.0  0.0   0:00.42 events/0
      7 root      15  -5     0    0    0 S  0.0  0.0   0:00.06 khelper
     41 root      15  -5     0    0    0 S  0.0  0.0   0:01.08 kblockd/
     67 root      15  -5     0    0    0 S  0.0  0.0   0:00.00 kseriod
    114 root      20   0     0    0    0 S  0.0  0.0   0:01.62 pdflush
    116 root      15  -5     0    0    0 S  0.0  0.0   0:02.44 kswapd0
  The system summary contains a lot of good stuff; see Table 10-3 for a rundown.
  Table 10-3: top Information Fields
    Row Field
  1 top 14:59:20
  up 6:30
           2 users
           load average:
  Meaning
  Name of the program.
  Current time of day.
  This is called uptime. It is the amount of time since the machine was last booted. In this example, the system has been up for 61⁄2 hours.
  Two users are logged in.
  Load average refers to the number of processes that are waiting to run; that is, the number of pro- cesses that are in a runnable state and are sharing the CPU. Three values are shown, each for a differ- ent period of time. The first is the average for the last 60 seconds, the next the previous 5 minutes, and finally the previous 15 minutes. Values under 1.0 indicate that the machine is not busy.
  (continued ) Processes 99

  Table 10-3 (continued ) Row Field
  Meaning
   2
  Tasks: This summarizes the number of processes and their various process states.
  0.7%us 0.7% of the CPU is being used for user processes. This means processes outside of the kernel itself.
  1.0%sy 1.0% of the CPU is being used for system (kernel) processes.
  0.0%ni 0.0% of the CPU is being used by nice (low-priority) processes.
  98.3%id 98.3% of the CPU is idle.
  0.0%wa 0.0% of the CPU is waiting for I/O.
  Mem: Shows how physical RAM is being used.
  Swap: Shows how swap space (virtual memory) is being used.
                    4 5
        The top program accepts a number of keyboard commands. The two most interesting are h, which displays the program’s help screen, and q, which quits top.
  Both major desktop environments provide graphical applications that display information similar to top (in much the same way that Task Manager in Windows does), but I find that top is better than the graphical versions because it is faster and consumes far fewer system resources. After all, our system monitor program shouldn’t add to the system slowdown that we are trying to track.
  Controlling Processes
  Now that we can see and monitor processes, let’s gain some control over them. For our experiments, we’re going to use a little program called xlogo as our guinea pig. The xlogo program is a sample program supplied with the X Window System (the underlying engine that makes the graphics on our display go), which simply displays a resizable window containing the X logo. First, we’ll get to know our test subject:
  [me@linuxbox ~]$ xlogo
  After we enter the command, a small window containing the logo should appear somewhere on the screen. On some systems, xlogo may print a warning message, but it may be safely ignored.
    100
  Chapter 10
  Note: If your system does not include the xlogo program, try using gedit or kwrite instead.
  We can verify that xlogo is running by resizing its window. If the logo is redrawn in the new size, the program is running.
  Notice how our shell prompt has not returned? This is because the shell is waiting for the program to finish, just like all the other programs we have used so far. If we close the xlogo window, the prompt returns.
  Interrupting a Process
  Let’s observe what happens when we run xlogo again. First, enter the xlogo command and verify that the program is running. Next, return to the ter- minal window and press CTRL-C.
  [me@linuxbox ~]$ xlogo [me@linuxbox ~]$
  In a terminal, pressing CTRL-C interrupts a program. This means that we politely asked the program to terminate. After we pressed CTRL-C, the xlogo window closed and the shell prompt returned.
  Many (but not all) command-line programs can be interrupted by using this technique.
  Putting a Process in the Background
  Let’s say we wanted to get the shell prompt back without terminating the xlogo program. We’ll do this by placing the program in the background. Think of the terminal as having a foreground (with stuff visible on the sur- face, like the shell prompt) and a background (with hidden stuff below the surface). To launch a program so that it is immediately placed in the back- ground, we follow the command with an ampersand character (&):
  [me@linuxbox ~]$ xlogo & [1] 28236
  [me@linuxbox ~]$
  After the command was entered, the xlogo window appeared and the shell prompt returned, but some funny numbers were printed too. This message is part of a shell feature called job control. With this message, the shell is telling us that we have started job number 1 ([1]) and that it has PID 28236. If we run ps, we can see our process:
  [me@linuxbox ~]$ ps
         PID TTY
  10603 pts/1
  28236 pts/1
  28239 pts/1
      TIME CMD
  00:00:00 bash
  00:00:00 xlogo
  00:00:00 ps
   Processes 101
  The shell’s job control facility also gives us a way to list the jobs that have been launched from our terminal. Using the jobs command, we can see the following list:
  [me@linuxbox ~]$ jobs
  [1]+ Running xlogo &
  The results show that we have one job, numbered 1, that it is running, and that the command was xlogo &.
  Returning a Process to the Foreground
  A process in the background is immune from keyboard input, including any attempt to interrupt it with a CTRL-C. To return a process to the foreground, use the fg command, as in this example:
  [me@linuxbox ~]$ jobs
  [1]+ Running xlogo & [me@linuxbox ~]$ fg %1
  xlogo
  The command fg followed by a percent sign and the job number (called a jobspec) does the trick. If we have only one background job, the jobspec is optional. To terminate xlogo, type CTRL-C.
  Stopping (Pausing) a Process
  Sometimes we’ll want to stop a process without terminating it. This is often done to allow a foreground process to be moved to the background. To stop a foreground process, type CTRL-Z. Let’s try it. At the command prompt, type xlogo, press the ENTER key, and then type CTRL-Z:
  [me@linuxbox ~]$ xlogo
  [1]+ Stopped xlogo [me@linuxbox ~]$
  After stopping xlogo, we can verify that the program has stopped by attempting to resize the xlogo window. We will see that it appears quite dead. We can either restore the program to the foreground, using the fg command, or move the program to the background with the bg command:
  [me@linuxbox ~]$ bg %1 [1]+ xlogo & [me@linuxbox ~]$
  As with the fg command, the jobspec is optional if there is only one job.
  Moving a process from the foreground to the background is handy if we launch a graphical program from the command but forget to place it in the background by appending the trailing &.
          102 Chapter 10
  Why would you want to launch a graphical program from the com- mand line? There are two reasons. First, the program you wish to run might not be listed on the window manager’s menus (such as xlogo).
  Second, by launching a program from the command line, you might be able to see error messages that would be invisible if the program were launched graphically. Sometimes, a program will fail to start up when launched from the graphical menu. By launching it from the command line instead, we may see an error message that will reveal the problem. Also, some graphical pro- grams have many interesting and useful command-line options.
  Signals
  The kill command is used to "kill" (terminate) processes. This allows us to end the execution of a program that is behaving badly or otherwise refuses to terminate on its own. Here’s an example:
  [me@linuxbox ~]$ xlogo &
  [1] 28401
  [me@linuxbox ~]$ kill 28401
  [1]+ Terminated xlogo
  We first launch xlogo in the background. The shell prints the jobspec and the PID of the background process. Next, we use the kill command and spe- cify the PID of the process we want to terminate. We could also have specified the process using a jobspec (for example, %1) instead of a PID.
  While this is all very straightforward, there is more to it. The kill com- mand doesn’t exactly "kill" processes; rather it sends them signals. Signals are one of several ways that the operating system communicates with pro- grams. We have already seen signals in action with the use of CTRL-C and CTRL-Z. When the terminal receives one of these keystrokes, it sends a signal to the program in the foreground. In the case of CTRL-C, a signal called INT (Interrupt) is sent; with CTRL-Z, a signal called TSTP (Terminal Stop) is sent. Programs, in turn, "listen" for signals and may act upon them as they are received. The fact that a program can listen and act upon signals allows it to do things like save work in progress when it is sent a termination signal.
  Sending Signals to Processes with kill
  The most common syntax for the kill command looks like this: kill [-signal] PID...
  If no signal is specified on the command line, then the TERM (Termin- ate) signal is sent by default. The kill command is most often used to send the signals shown in Table 10-4.
    Processes 103
  Table 10-4: Common Signals
   Number Name
  1 HUP
  Meaning
  Hang up. This is a vestige of the good old days when terminals were attached to remote computers with phone lines and modems. The signal is used to indicate to programs that the controlling ter- minal has "hung up." The effect of this signal can be demonstrated by closing a terminal session. The foreground program running on the terminal will be sent the signal and will terminate.
  This signal is also used by many daemon programs to cause a reinitialization. This means that when a daemon is sent this signal, it will restart and reread its configuration file. The Apache web server is an example of a daemon that uses the HUP signal in this way.
  Interrupt. Performs the same function as the CTRL-C key sent from the terminal. It will usually terminate a program.
  Kill. This signal is special. Whereas programs may choose to handle signals sent to them in different ways, including by ignoring them altogether, the KILL signal is never actually sent to the target program. Rather, the kernel immediately termin- ates the process. When a process is terminated in this manner, it is given no opportunity to "clean up" after itself or save its work. For this reason, the KILL signal should be used only as a last resort when other termination signals fail.
  Terminate. This is the default signal sent by the kill command. If a program is still "alive" enough to receive signals, it will terminate.
  Continue. This will restore a process after a STOP signal.
  Stop. This signal causes a process to pause without terminating. Like the KILL signal, it is not sent to the target process, and thus it cannot be ignored.
     2 INT
  9 KILL
        15 TERM
  18 CONT
  19 STOP
           104 Chapter 10
  Let’s try out the kill command:
  [me@linuxbox ~]$ xlogo &
  [1] 13546
  [me@linuxbox ~]$ kill -1 13546
  [1]+ Hangup xlogo
  In this example, we start the xlogo program in the background and then send it a HUP signal with kill. The xlogo program terminates, and the shell indicates that the background process has received a hangup signal. You may need to press the ENTER key a couple of times before you see the mes- sage. Note that signals may be specified either by number or by name, including the name prefixed with the letters SIG:
  [me@linuxbox ~]$ xlogo &
  [1] 13601
  [me@linuxbox ~]$ kill -INT 13601 [1]+ Interrupt xlogo [me@linuxbox ~]$ xlogo &
  [1] 13608
  [me@linuxbox ~]$ kill -SIGINT 13608 [1]+ Interrupt xlogo
  Repeat the example above and try out the other signals. Remember, you can also use jobspecs in place of PIDs.
  Processes, like files, have owners, and you must be the owner of a pro- cess (or the superuser) in order to send it signals with kill.
  In addition to the signals listed in Table 10-4, which are most often used with kill, other signals are frequently used by the system. Table 10-5 lists the other common signals.
  Table 10-5: Other Common Signals
       Number Name
  3 QUIT 11 SEGV
  20 TSTP
  28 WINCH
  Meaning
  Quit.
  Segmentation violation. This signal is sent if a program makes illegal use of memory; that is, it tried to write somewhere it was not allowed to.
  Terminal stop. This is the signal sent by the terminal when CTRL-Z is pressed. Unlike the STOP signal, the
  TSTP signal is received by the program but the pro- gram may choose to ignore it.
  Window change. This is a signal sent by the system when a window changes size. Some programs,
  like top and less, will respond to this signal by redrawing themselves to fit the new window dimensions.
              Processes 105
  For the curious, a complete list of signals can be seen with the following command:
  [me@linuxbox ~]$ kill -l
  Sending Signals to Multiple Processes with killall
  It’s also possible to send signals to multiple processes matching a specified program or username by using the killall command. Here is the syntax:
  killall [-u user] [-signal] name...
  To demonstrate, we will start a couple of instances of the xlogo program
    and then terminate them:
  [me@linuxbox ~]$ xlogo & [1] 18801
  [me@linuxbox ~]$ xlogo & [2] 18802
  [me@linuxbox ~]$ killall xlogo [1]- Terminated
  [2]+ Terminated
  xlogo xlogo
    Remember, as with kill, you must have superuser privileges to send sig- nals to processes that do not belong to you.
  More Process-Related Commands
  Since monitoring processes is an important system administration task, there are a lot of commands for it. Table 10-6 lists some to play with.
  Table 10-6: Other Process-Related Commands
  Command
  pstree
  vmstat
  xload tload
  Description
  Outputs a process list arranged in a tree-like pattern showing the parent/child relationships between processes.
  Outputs a snapshot of system resource usage including memory, swap, and disk I/O. To see a continuous display, follow the command with a time delay (in seconds) for updates (e.g., vmstat 5). Terminate the output with CTRL-C.
  A graphical program that draws a graph showing system load over time.
  Similar to the xload program, but draws the graph in the terminal. Terminate the output with CTRL-C.

  12.1.1 Foreground and Background

  UNIX distinguishes between foreground and background programs. This feature allows you to run several programs simultaneously from your terminal. When a program is running in the foreground, anything you type at the keyboard is sent to the program's standard input unless you have redirected it. As a result, you can't do anything else until the program finishes. When you run a program in the background, it is disconnected from the keyboard. Anything you type reaches the UNIX shell and is interpreted as a command. Therefore, you can run many programs simultaneously in the background. You can run only one program at a time in the foreground.

  To run a program in the background, type an ampersand ( & ) at the end of the command line. For example:

      %

      f77 program.F &


      [1] 9145
      %

  This runs a FORTRAN compilation in the background, letting you continue other work while the compilation proceeds. The shell responds by printing a job number in brackets ( [] ), followed by the process identification (PID) number ( 38.3 ) for the command. It then prompts you for a new command. Entering the command jobs produces a short report describing all the programs you are executing in the background. For example:

      %

      f77 program.F &


      [1] 9145
      %

      jobs


      [1]     + Running       f77 program.F
      %

  To bring a program from the background into the foreground, use the foreground command, fg . If you have more than one background job, follow fg with a job identifier - a percent sign ( % ) followed by the job number:

      %

      jobs


      [1]     - Running       f77 program.F
      [2]     + Stopped       vi sinus.F
      %

      fg %1

  The plus sign ( + ) in the report from jobs indicates which job will return to the foreground by default ( 12.3 ) .

  To suspend a job running in the foreground, press CTRL-z. [You can use this to stop most frozen or runaway programs until you figure out what to do next. Also, CTRL-z can stop programs that interrupt characters ( 5.9 ) like CTRL-c can't. -JP  ]

  Entering the background command, bg , lets a stopped program continue execution in the background. The foreground command, fg , restores this program to execution in the foreground. For example:

      %

      f77 -o program program.F



      [CTRL-z]

      Stopped
      %

      bg


      [1]     + Running       f77 -o program program.F
      %

  There is no prompt after the f77 command because the compiler is running in the foreground. After you press CTRL-z, the shell prints the word "Stopped" to indicate that it has stopped execution. At this point, you can enter any command; the bg command lets the job continue executing in the background. This feature is useful if you forget to type an & at the end of the command line or if you decide to do something else while the job is running.

  To terminate a background job, you can use the command's job number rather than its PID number, as follows:

      %

      kill %1

  If you omit it, UNIX interprets the job number as a process number. This will probably be the process number of some operating system function. UNIX will not let you make such a mistake unless you are superuser ( 1.24 ) . If you are superuser, the command is fatal. You may be superuser from time to time and therefore should not develop sloppy habits.

  In the next few seconds, press RETURN a few times. You should see the message:

      [1]  Terminated    f77 -o program program.F

  If you don't see that, use the jobs command to check whether the job is still running. If it's still running, use the -9 option as a last resort:

      %

      kill -9 %1


      [1]  Killed        f77 -o program program.F

  The -9 option doesn't give the process a chance to clean up its temporary files and exit gracefully, so don't use it unless you need to.

  A program running in the background cannot read input from a terminal. If a background job needs terminal input, it will stop; the jobs command will print the message Stopped (tty input) . Before the program can continue, you must bring it into the foreground with the fg command and type the required input. You can save yourself this trouble by redirecting the program's input so that it reads all its data from a file. You may also want to redirect standard output and standard error. If you don't, any output the program produces will appear on your terminal (unless you've used stty tostop ( 12.7 ) ). Since you will probably be using other commands, having miscellaneous data and other messages flying across your terminal may be confusing.

  On systems and shells without job control features, an & will start a command in the background. It is impossible to move a job from the foreground to the background or vice versa. The ps ( 38.5 ) command is the only tool available for determining what background jobs you have running.

  Two commands, time and /bin/time , provide simple timings. Their information is highly accurate, because no profiling overhead distorts the program's performance. Neither program provides any analysis on the routine or trace level. They report the total execution time, some other global statistics, and nothing more. You can use them on any program.

  time and /bin/time differ primarily in that time is built into the C shell. Therefore, it cannot be used in Bourne shell scripts or in makefiles. It also cannot be used if you prefer the Bourne shell ( sh ). /bin/time is an independent executable file and therefore can be used in any situation. To get a simple program timing, enter either time or /bin/time , followed by the command you would normally use to execute the program. For example, to time a program named analyze , enter the following command:

      %

      time analyze inputdata outputfile


      9.0u 6.7s 0:30 18% 23+24k 285+148io 625pf+0w

  This indicates that the program spent 9.0 seconds on behalf of the user (user time), 6.7 seconds on behalf of the system (system time, or time spent executing UNIX kernel routines on the user's behalf), and a total of 30 seconds elapsed time. Elapsed time is the wall clock time from the moment you enter the command until it terminates, including time spent waiting for other users, I/O time, etc.

  By definition, the elapsed time is greater than your total CPU time and can even be several times larger. You can set programs to be timed automatically (without typing time first) or change the output format by setting the csh time variable ( 39.3 ) .

  The example above shows the CPU time as a percentage of the elapsed time (18 percent). The remaining data report virtual memory management and I/O statistics. The meaning varies, depending on your shell; check your online csh manual page or article 39.3 .

  In this example, under SunOS 4.1.1, the other fields show the amount of shared memory used, the amount of nonshared memory used ( k ), the number of block input and output operations ( io ), and the number of page faults plus the number of swaps ( pf and w ). The memory management figures are unreliable in many implementations, so take them with a grain of salt.

  /bin/time reports only the real time (elapsed time), user time, and system time. For example:

      %

      /bin/time analyze inputdata outputfile


             60.8 real        11.4 user         4.6 sys

  [If you use the Bourne shell, you can just type time . -JP  ] This reports that the program ran for 60.8 seconds before terminating, using 11.4 seconds of user time and 4.6 seconds of system time, for a total of 16 seconds of CPU time.

  There's a third timer on many systems: timex . It can give much more detail if your system has process accounting enabled. Check the timex (1) manpage.

  Article 39.5 has more about the terms used in this article.

  UNIX Power Tools
  Previous: 40.11 Send Yourself Reminder Mail 	Chapter 40
  Delayed Execution 	Next: 40.13 Adding crontab Entries

  40.12 Periodic Program Execution: The cron Facility

  cron allows you to schedule programs for periodic execution. For example, you can use cron to call a particular UUCP ( 1.33 ) site every hour, to clean up editor backup files every night, or to perform any number of other tasks. However, cron is not a general facility for scheduling program execution off-hours; use the at command ( 40.3 ) .

  With redirection ( 13.1 ) , cron can send program output to a log file or to any username via the mail system ( 1.33 ) .

      NOTE: cron jobs are run by a system program in an environment that's much different from your normal login sessions. The search path ( 8.7 ) is usually shorter; you may need to use absolute pathnames for programs that aren't in standard system directories. Be careful about using command aliases, shell functions and variables, and other things that may not be set for you by the system.

  40.12.1 Execution Scheduling

  The cron system is serviced by the cron daemon ( 1.14 ) . What to run and when to run it are specified to cron by crontab entries, which are stored in the system's cron schedule. Under BSD, this consists of the files /usr/lib/crontab and /usr/lib/crontab.local ; either file may be used to store crontab entries. Both are ASCII files and may be modified with any text editor. Since usually only root has access to these files, all cron scheduling must go through the system administrator. This can be either an advantage or a disadvantage, depending on the needs and personality of your site.

  Under System V (and many other versions of UNIX), any user may add entries to the cron schedule. crontab entries are stored in separate files for each user. The crontab files are not edited directly by ordinary users, but are placed there with the crontab command (described later in this section). [In my experience, the cron jobs are run from your home directory. If you read a file or redirect output to a file with a relative pathname ( 14.2 ) , that'll probably be in your home directory. Check your system to be sure. -JP  ]

  crontab entries direct cron to run commands at regular intervals. Each one-line entry in the crontab file has the following format:

      mins hrs day-of-month month weekday username cmd (BSD)
      mins hrs day-of-month month weekday cmd (System V)

  Spaces separate the fields. However, the final field, cmd , can contain spaces within it (i.e., the cmd field consists of everything after the space following weekday ); the other fields must not contain spaces. The username field is used in the BSD version only and specifies the username under which to run the command. Under System V, commands are run by the user who owns the crontab in which they appear (and for whom it is named).

  The first five fields specify the times at which cron should execute cmd . Their meanings are described in Table 40.1 .
  Table 40.1: crontab Entry Time Fields Field 	Meaning 	Range
  mins 	The minutes after the hour. 	0-59
  hrs 	The hours of the day. 	0-23 (0 = midnight)
  day-of-month 	The day within a month. 	1-31
  month 	The month of the year. 	1-12
  weekday 	The day of the week. 	1-7 (1 = Monday) BSD
      0-6 (0=Sunday) System V

  These fields can contain a single number, a pair of numbers separated by a dash (indicating a range of numbers), a comma-separated list of numbers and ranges, or an asterisk (a wildcard that represents all valid values for that field).

  If the first character in an entry is a hash mark (#), cron will treat the entry as a comment and ignore it. This is an easy way to temporarily disable an entry without permanently deleting it.

  Here are some example crontab entries (shown in System V format):






  2>&1




  \%





  0,15,30,45 * * * *  (echo -n '   '; date; echo "") >/dev/console
  0,10,20,30,40,50 7-18 * * * /usr/lib/atrun
  7 0 * * *  find / -name "*.bak" -type f -atime +7 -exec rm {} \;
  12 4 * * *  /bin/sh /usr/adm/ckdsk >/usr/adm/disk.log 2>&1
  22 2 * * *  /bin/sh /usr/adm/ckpwd 2>&1 | mail root
  30 3 * * 1 /bin/csh -f /usr/lib/uucp/uu.weekly >/dev/null 2>&1
  12 5 15-21 * * test `date +\%a` = Mon && /usr/local/etc/mtg-notice
  #30 2 * * 0,6  /usr/lib/newsbin/news.weekend

  The first entry displays the date on the console terminal every fifteen minutes (on the quarter hour); notice that multiple commands are enclosed in parentheses in order to redirect their output as a group. (Technically, this says to run the commands together in a subshell ( 13.7 ) .) The second entry runs /usr/lib/atrun every ten minutes from 7:00 a.m. to 6:00 p.m. daily. The third entry runs a find command at seven minutes after midnight to remove all .bak files not accessed in seven days. [To cut wear and tear and load on your disk, try to combine find jobs ( 23.22 ) . Also, as article 40.5 explains, try not to schedule your jobs at often-chosen times like 1:00 a.m., 2:00 a.m., and so on; pick oddball times like 4:12 a.m. -JP  ]

  The fourth and fifth lines run a shell script every day, at 4:12 a.m. and 2:22 a.m., respectively. The shell to execute the script is specified explicitly on the command line in both cases; the system default shell, usually the Bourne shell, is used if none is explicitly specified. Both lines' entries redirect standard output and standard error, sending it to a file in one case and mailing it to root in the other.

  The sixth entry executes a C shell script named uu.weekly , stored in /usr/lib/uucp , at 3:30 a.m. on Monday mornings. Notice that the command format - specifically the output redirection - is for the Bourne shell even though the script itself will be run under the C shell. The seventh entry runs on the third Monday of every month; there's more explanation below. The final entry would run the command /usr/lib/newsbin/news.weekend at 2:30 a.m. on Saturday and Sunday mornings if it were not disabled with a # . ( # can also be used to add comments to your crontab .)

  The fourth through sixth entries illustrate three output-handling alternatives: redirecting it to a file, piping it through mail, and discarding it to /dev/null ( 13.14 ) . If no output redirection is performed, the output is sent via mail to the user who ran the command.

  The cmd field can be any UNIX command or group of commands (properly separated with semicolons). The entire crontab entry can be arbitrarily long, but it must be a single physical line in the file.

  One problem with the crontab syntax is that it lets you specify any day of the month, and any day of the week; but it doesn't let you construct cases like "the third Monday of every month." You might think that the crontab entry:

      12 5 15-21 * 1

      your-command

  would do the trick, but it won't; this crontab entry runs your command on every Monday, plus the 15th through the 21st of each month. [1] An answer from Greg Ubben is shown in the seventh entry. He uses the test ( 44.20 ) and date ( 51.10 ) commands to compare the name of today (like Tue ) to the day we want the entry to be executed (here, Mon ). This entry will be run between the 15th and 21st of each month, but the mtg-notice command will only run on the Monday during that period. The shell's && operator ( 44.9 ) runs the mtg-notice command only when the previous test succeeds. Greg actually writes the entry as shown here, testing for failure of the test command:

      [1] This strange behavior seems to be a System V peculiarity that somehow infected the rest of the world. "True" BSD systems behave the way we explained earlier. However, SunOS 4.X systems have incorporated System V's behavior; and, with the advent of Solaris, there are relatively few true commercial BSD systems left in the world.

      12 5 15-21 * * test `date +\%a` != Mon || /usr/local/etc/mtg-notice

  He did it in that "backwards" way so the cron job's exit status would be 0 (success) in the case when it doesn't execute mtg-notice . You may need that technique, too.

  The cron command starts the cron program. It has no options. Once started, cron never terminates. It is normally started automatically by one of the system initialization scripts. cron reads the crontab file(s) every minute to see whether there have been changes. Therefore, any change to its schedule will take effect within one minute.

  - AF , JP

  The at facility submits a command line (or a script) for execution at an arbitrary later time. It has the form:

    %

    at



    options time < scriptfile

  This submits the scriptfile for execution at a later time . The redirection ( < ) isn't required on BSD and some other UNIX systems. If you don't want to write a script, you can omit it and type your commands on the terminal, terminated by CTRL-d:

      %

      at



      options time
      Command 1
      Command 2


      ...

      [CTRL-d]

  The time is most commonly a four-digit number representing a time on a 24-hour clock. For example, 0130 represents 1:30 a.m. and 1400 represents 2 p.m. You can also use abbreviations such as 1am , 130pm , and so on.

  11.9 Using date and cron to Run a Script on the Nth Day

  Problem
  You need to run a script on the Nth weekday of the month (e.g., the second Wednes- day), and most crons will not allow that.
  Solution
  Use a bit of shell code in the command to be run. In your Linux Vixie Cron crontab adapt one of the following lines. If you are using another cron program, you may need to convert the day of the week names to numbers according to the schedule your cron uses (0–6 or 1–7) and use +%w (day of week as number) in place of +%a (locale’s abbreviated weekday name):
       # Vixie Cron
       # Min   Hour DoM   Mnth DoW Program
       # 0-59 0-23 1-31 1-12 0-7
       # Run the first Wednesday @ 23:00
       00 23 1-7 * Wed [ "$(date '+%a')" == "Wed" ] && /path/to/command args to command
       # Run the second Thursday @ 23:00
       00 23 8-14 * Thu [ "$(date '+%a')" == "Thu" ] && /path/to/command
       # Run the third Friday @ 23:00
       00 23 15-21 * Fri [ "$(date '+%a')" == "Fri" ] && /path/to/command
       # Run the fourth Saturday @ 23:00
       00 23 22-27 * Sat [ "$(date '+%a')" == "Sat" ] && /path/to/command
       # Run the fifth Sunday @ 23:00
       00 23 28-31 * Sun [ "$(date '+%a')" == "Sun" ] && /path/to/command
  Note that any given day of the week doesn’t always happen five times during one month, so be sure you really know what you are asking for if you schedule something for the fifth week of the month.
    228
  | Chapter 11: Working with Dates and Times
  Discussion
  Most versions of cron (including Linux’s Vixie Cron) do not allow you to schedule a job on the Nth day of the month. To get around that, we schedule the job to run dur- ing the range of days when the Nth day we need occurs, then check to see if it is the correct day on which to run. The "second Wednesday of the month" must occur somewhere in the range of the 8th to 14th day of the month. So we simply run every day and see if it’s Wednesday. If so, we execute our command.
  Table 11-2 shows the ranges noted above.
  Table 11-2. Day ranges for each week of a month
  Week
  First
  Second
  Third
  Fourth
  Fifth (see previous warning note)
  Day range
  1 to 7
  8 to 14 15 to 21 22 to 27 28 to 31
   We know this almost seems too simplistic; check a calendar if you don’t believe us:
      $ cal 10 2006
          October 2006
  S M Tu W Th F S 1234567 8 9 10 11 12 13 14
      15 16 17 18 19 20 21
      22 23 24 25 26 27 28
      29 30 31



### VO 600w

  ps—Report a snapshot of current processes.
  pstree

  psa

  top—Display tasks.
  open -a 'activity monitor'
  htop

  kill—Send a signal to a process.
  killall—Kill processes by name.

  kill -TERM
  kill -9

  jobs—List active jobs.
  bg—Place a job in the background.
  fg—Place a job in the foreground.

  To run a program in the background, type an ampersand ( & ) at the end of the command line. For example:

      %

      f77 program.F &


      [1] 9145
      %

  This runs a FORTRAN compilation in the background, letting you continue other work while the compilation proceeds. The shell responds by printing a job number in brackets ( [] ), followed by the process identification (PID) number ( 38.3 ) for the command. It then prompts you for a new command. Entering the command jobs produces a short report describing all the programs you are executing in the background. For example:

      %

      f77 program.F &


      [1] 9145
      %

      jobs


      [1]     + Running       f77 program.F
      %

  To bring a program from the background into the foreground, use the foreground command, fg . If you have more than one background job, follow fg with a job identifier - a percent sign ( % ) followed by the job number:

      %

      jobs


      [1]     - Running       f77 program.F
      [2]     + Stopped       vi sinus.F
      %

      fg %1

  The plus sign ( + ) in the report from jobs indicates which job will return to the foreground by default ( 12.3 ) .

  To suspend a job running in the foreground, press CTRL-z. [You can use this to stop most frozen or runaway programs until you figure out what to do next. Also, CTRL-z can stop programs that interrupt characters ( 5.9 ) like CTRL-c can't. -JP  ]

  Entering the background command, bg , lets a stopped program continue execution in the background. The foreground command, fg , restores this program to execution in the foreground. For example:

      %

      f77 -o program program.F



      [CTRL-z]

      Stopped
      %

      bg


      [1]     + Running       f77 -o program program.F
      %

  There is no prompt after the f77 command because the compiler is running in the foreground. After you press CTRL-z, the shell prints the word "Stopped" to indicate that it has stopped execution. At this point, you can enter any command; the bg command lets the job continue executing in the background. This feature is useful if you forget to type an & at the end of the command line or if you decide to do something else while the job is running.

  To terminate a background job, you can use the command's job number rather than its PID number, as follows:

      %

      kill %1

  If you omit it, UNIX interprets the job number as a process number. This will probably be the process number of some operating system function. UNIX will not let you make such a mistake unless you are superuser ( 1.24 ) . If you are superuser, the command is fatal. You may be superuser from time to time and therefore should not develop sloppy habits.

  In the next few seconds, press RETURN a few times. You should see the message:

      [1]  Terminated    f77 -o program program.F

  If you don't see that, use the jobs command to check whether the job is still running. If it's still running, use the -9 option as a last resort:

      %

      kill -9 %1


      [1]  Killed        f77 -o program program.F

  The -9 option doesn't give the process a chance to clean up its temporary files and exit gracefully, so don't use it unless you need to.

  A program running in the background cannot read input from a terminal. If a background job needs terminal input, it will stop; the jobs command will print the message Stopped (tty input) .

  /bin/time reports only the real time (elapsed time), user time, and system time. For example:

      %

      /bin/time analyze inputdata outputfile


             60.8 real        11.4 user         4.6 sys

  cron allows you to schedule programs for periodic execution. For example, you can use cron to call a particular UUCP ( 1.33 ) site every hour, to clean up editor backup files every night, or to perform any number of other tasks. However, cron is not a general facility for scheduling program execution off-hours; use the at command ( 40.3 ) .

  With redirection ( 13.1 ) , cron can send program output to a log file or to any username via the mail system ( 1.33 ) .

    NOTE: cron jobs are run by a system program in an environment that's much different from your normal login sessions. The search path ( 8.7 ) is usually shorter; you may need to use absolute pathnames for programs that aren't in standard system directories. Be careful about using command aliases, shell functions and variables, and other things that may not be set for you by the system.


  mins 	The minutes after the hour. 	0-59
  hrs 	The hours of the day. 	0-23 (0 = midnight)
  day-of-month 	The day within a month. 	1-31
  month 	The month of the year. 	1-12
  weekday 	The day of the week. 	1-7 (1 = Monday) BSD
   0-6 (0=Sunday) System V


  The at facility submits a command line (or a script) for execution at an arbitrary later time. It has the form:

    %

    at



    options time < scriptfile

  This submits the scriptfile for execution at a later time . The redirection ( < ) isn't required on BSD and some other UNIX systems. If you don't want to write a script, you can omit it and type your commands on the terminal, terminated by CTRL-d:

      %

      at


      options time
      Command 1
      Command 2


      ...

      [CTRL-d]

  The time is most commonly a four-digit number representing a time on a 24-hour clock. For example, 0130 represents 1:30 a.m. and 1400 represents 2 p.m. You can also use abbreviations such as 1am , 130pm , and so on.

  https://developer.apple.com/library/mac/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/ScheduledJobs.html

## Package management 2m

  https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/Installation.md

  Get Xcode
  Get Xcode 6.3 .
  xcode 6.1 for yosemite
  Download and install it, you also need to open Xcode agree to the license and it will install its components.

  yosemite-xcode-install
  Get Command Line Tools

  xcode-select --install

  Install Homebrew

  To download install Homebrew run the install script on the command line as below and let the script do its thing:

  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

  homebrew-osx-install-mountain-lion

  Download and install Xquartz brew will moan if it is not installed.

  After installing and as suggested in the command line, to check for any issues with the install run:

  brew doctor

  To search for an application:

  brew search

  To install

  brew install <application-name>

  To list all apps installed by Homebrew

  brew list

  To remove an installed application

  brew remove <application-name>

  To update Homebrew

  brew update

  To see what else you can do

  man brew

  Where does Homebrew install stuff …. in the Cellar

  /usr/local/Cellar/


  Skip to content
  This repository

      Pull requests
      Issues
      Gist

      @kmcd
  183
  7,871

      2,862

  caskroom/homebrew-cask

  homebrew-cask/USAGE.md
  4caa121 21 days ago
  @vitorgalvao vitorgalvao usage: add '$' to completion commands
  14 contributors
  @rolandwalker
  @vitorgalvao
  @phinze
  @adamchainz
  @tpitale
  @voanhduy1512
  @ujovlado
  @leoj3n
  @jedahan
  @xyb
  @hanjianwei
  @linc01n
  @Cottser
  @pasku
  242 lines (167 sloc) 9.2 KB
  How to Use Homebrew-cask
  Getting Started

  First ensure you have Homebrew version 0.9.5 or higher:

  $ brew --version
  0.9.5

  Install the homebrew-cask tool:

  $ brew install caskroom/cask/brew-cask

  Frequently Used Commands

  Homebrew-cask is implemented as a subcommand of Homebrew. All homebrew-cask commands begin with brew cask. Homebrew-cask has its own set of command verbs many of which are similar to Homebrew’s. The most frequently-used commands are:

      search — searches all known Casks
      install — installs the given Cask
      uninstall — uninstalls the given Cask

  Searching for Casks

  The brew cask search command accepts a series of substring arguments, and returns tokens representing matching Casks. Let’s see if there’s a Cask for Google Chrome:

  $ brew cask search chrome
  google-chrome

  A search command with no search term will list all available Casks:

  $ brew cask search
  # <list of all available Casks>

  Installing Casks

  The command brew cask install accepts a Cask token as returned by brew cask search. Let’s try to install Google Chrome:

  $ brew cask install google-chrome
  ==> Downloading https://dl.google.com/chrome/mac/stable/GGRO/googlechrome.dmg
  ==> Success! google-chrome installed to /opt/homebrew-cask/Caskroom/google-chrome/stable-channel
  ==> Linking Google Chrome.app to /Users/paulh/Applications/Google Chrome.app

  Uninstalling Casks

  Easy peasy:

  $ brew cask uninstall google-chrome

  This will both uninstall the Cask and remove symlinks which were created in ~/Applications.

  To uninstall all versions of a Cask, use --force:

  $ brew cask uninstall --force google-chrome

  Note that uninstall --force is currently imperfect. See the man page for more information.
  Other Commands

      info — displays information about the given Cask
      list — with no args, lists installed Casks; given installed Casks, lists staged files
      fetch — downloads Cask resources to local cache (with --force, re-download even if already cached)
      doctor — checks for configuration issues
      cleanup — cleans up cached downloads (with --outdated, only cleans old downloads)
      home — opens the homepage of the given Cask; or with no arguments, the homebrew-cask project page
      update — a synonym for brew update
      zap — try to remove all files associated with a Cask (including resources which may be shared with other applications)

  The following commands are for Cask authors:

      audit — verifies installability of Casks
      cat — dumps the given Cask to the standard output
      create — creates a Cask and opens it in an editor
      edit — edits the given Cask

  The following aliases and abbreviations are provided for convenience:

      ls — list
      -S — search
      rm, remove — uninstall
      up — update
      dr — doctor

  Tab Completion

  Homebrew/homebrew-completions supports bash and fish completions (only for brew-cask right now). Install them with:

  $ brew install homebrew/completions/brew-cask-completion

  For zsh completion support, simply run:

  $ brew install `zsh-completions`

  Inspecting Installed Casks

  List all installed Casks

  $ brew cask list
  adium          google-chrome     onepassword

  Show details about a specific Cask:

  $ brew cask info caffeine
  caffeine: 1.1.1
  http://lightheadsw.com/caffeine/
  Not installed
  https://github.com/caskroom/homebrew-cask/blob/master/Casks/caffeine.rb

  Updating/Upgrading Casks

  Since the homebrew-cask repository is a Homebrew Tap, you’ll pull down the latest Casks every time you issue the regular Homebrew command brew update. Currently, homebrew-cask cannot always detect if an Application has been updated. You can force an update via the command brew cask install --force. We are working on improving this.

  It is generally safe to run updates from within an Application.
  Updating/Upgrading the Homebrew-cask Tool

  When a new version homebrew-cask is released, it will appear in the output of brew outdated after running brew update. You can upgrade it via the normal Homebrew brew upgrade workflow:

  $ brew update && brew upgrade brew-cask && brew cleanup && brew cask cleanup

  Additional Taps (optional)

  The primary homebrew-cask Tap includes most of the Casks that a typical user will be interested in. There are a few additional Taps where we store different kinds of Casks.
  Tap name 	description
  caskroom/versions 	contains alternate versions of Casks (e.g. betas, nightly releases, old versions)
  caskroom/fonts 	contains Casks that install fonts, which are kept separate so we can educate users about the different licensing landscape around font installation/usage
  caskroom/unofficial 	contains Casks that install unofficial builds or forks

  There are also alternate Cask Taps maintained by users.

  You can tap any of the above with a brew tap command:

  $ brew tap <tap_name>

  after which, Casks from the new Tap will be available to search or install just like Casks from the main Tap. brew update will automatically keep your new Tap up to date.

  You may also specify a fully-qualified Cask token (which includes the Tap) for any brew cask command. This will implicitly add the Tap if you have not previously added it with brew tap:

  $ brew cask install caskroom/fonts/font-symbola

  Options

  brew cask accepts a number of options:

      --version: print version and exit
      --debug: output debug information
      --no-binaries: skip symlinking executable binaries into /usr/local/bin

  You can also modify the default installation locations used when issuing brew cask install:

      --caskroom=/my/path determines where the actual applications will be located. Should be handled with care — setting it outside /opt or your home directory might mess up your system. Default is /opt/homebrew-cask/Caskroom.
      --appdir=/my/path changes the path where the symlinks to the applications (above) will be generated. This is commonly used to create the links in the root Applications directory instead of the home Applications directory by specifying --appdir=/Applications. Default is ~/Applications.
      --prefpanedir=/my/path changes the path for PreferencePane symlinks. Default is ~/Library/PreferencePanes
      --qlplugindir=/my/path changes the path for Quicklook Plugin symlinks. Default is ~/Library/QuickLook
      --fontdir=/my/path changes the path for Fonts symlinks. Default is ~/Library/Fonts
      --binarydir=/my/path changes the path for binary symlinks. Default is /usr/local/bin
      --input_methoddir=/my/path changes the path for Input Methods symlinks. Default is ~/Library/Input Methods
      --screen_saverdir=/my/path changes the path for Screen Saver symlinks. Default is ~/Library/Screen Savers

  To make these settings persistent, you might want to add the following line to your .bash_profile or .zshenv:

  # Specify your defaults in this environment variable
  export HOMEBREW_CASK_OPTS="--appdir=/Applications --caskroom=/etc/Caskroom"

  Note that you still can override the environment variable HOMEBREW_CASK_OPTS by explicitly providing options in the command line:

  # Will force the Chrome app to be linked to ~/Applications
  # even though HOMEBREW_CASK_OPTS specified /Applications
  $ brew cask install --appdir="~/Applications" google-chrome

  Advanced searching

  The default search algorithm is a lax substring approach, which does not use the command-line arguments exactly as given. If you need to specify a search more precisely, a single search argument enclosed in / characters will be taken as a Ruby regular expression:

  $ brew cask search '/^google.c[a-z]rome$/'
  google-chrome

  Other Ways to Specify a Cask

  Most brew cask commands can accept a Cask token as an argument. As described above, the token on the command line can take the form of:

      A token as returned by brew cask search, eg: google-chrome.
      A fully-qualified token which includes the Tap, eg: caskroom/fonts/font-symbola.

  brew cask also accepts three other forms as arguments

      A path to a Cask file, eg: /usr/local/Cellar/brew-cask/0.25.0/Casks/google-chrome.rb.
      A curl-retrievable URI to a Cask file, eg: https://raw.github.com/caskroom/homebrew-cask/f54bbfaae0f2fa7210484f46313a459cb8a14d2f/Casks/google-chrome.rb.
      A file in the current working directory, eg: my-modfied-google-chrome.rb. Note that matching Tapped Cask tokens will be preferred over this form when there is a conflict. To force the use of a Cask file in the current directory, specify a pathname with slashes, eg: ./google-chrome.rb.

  The last three forms are intended for users who wish to maintain private Casks.
  Taps

  You can add Casks to your existing (or new) Taps: just create a directory named Casks inside your Tap, put your Cask files there, and everything will just work.

    Status API Training Shop Blog About Pricing

    © 2015 GitHub, Inc. Terms Privacy Security Contact Help


  brew cask search font | sed '/Partial/d' | xargs brew cask info | grep http | xargs open



### VO 300w
  https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/Installation.md

  Get Xcode
  Get Xcode 6.3 .
  xcode 6.1 for yosemite
  Download and install it, you also need to open Xcode agree to the license and it will install its components.

  yosemite-xcode-install
  Get Command Line Tools

  xcode-select --install


  Install Homebrew

  To download install Homebrew run the install script on the command line as below and let the script do its thing:

  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

  Download and install Xquartz brew will moan if it is not installed.

  After installing and as suggested in the command line, to check for any issues with the install run:

  brew doctor

  To search for an application:

  brew search

  To install

  brew install <application-name>

  To list all apps installed by Homebrew

  brew list

  To remove an installed application

  brew remove <application-name>

  To update Homebrew

  brew update

  To see what else you can do

  man brew

  Where does Homebrew install stuff …. in the Cellar

  caskroom/homebrew-cask

  Homebrew-cask is implemented as a subcommand of Homebrew. All

  homebrew-cask commands begin with brew cask. Homebrew-cask has its own set of command verbs many of which are similar to Homebrew’s. The most frequently-used commands are:

      search — searches all known Casks
      install — installs the given Cask
      uninstall — uninstalls the given Cask

  Searching for Casks

  $ brew cask search chrome
  google-chrome

  A search command with no search term will list all available Casks:

  $ brew cask search
  # <list of all available Casks>

  Installing Casks

  The command brew cask install accepts a Cask token as returned by brew cask search. Let’s try to install Google Chrome:

  $ brew cask install google-chrome
  $ brew cask uninstall google-chrome

  This will both uninstall the Cask and remove symlinks which were created in ~/Applications.

  To uninstall all versions of a Cask, use --force:

  $ brew cask uninstall --force google-chrome

  Note that uninstall --force is currently imperfect. See the man page for more information.

  Other Commands

  info — displays information about the given Cask
  list — with no args, lists installed Casks; given installed Casks, lists staged files
  fetch — downloads Cask resources to local cache (with --force, re-download even if already cached)
  doctor — checks for configuration issues
  cleanup — cleans up cached downloads (with --outdated, only cleans old downloads)
  home — opens the homepage of the given Cask; or with no arguments, the homebrew-cask project page
  update — a synonym for brew update
  zap — try to remove all files associated with a Cask (including resources which may be shared with other applications)

  Tab Completion

  Homebrew/homebrew-completions supports bash and fish completions (only for brew-cask right now). Install them with:

  $ brew install homebrew/completions/brew-cask-completion

  List all installed Casks

  $ brew cask list
  adium          google-chrome     onepassword

  Show details about a specific Cask:

  $ brew cask info caffeine
  caffeine: 1.1.1
  http://lightheadsw.com/caffeine/
  Not installed
  https://github.com/caskroom/homebrew-cask/blob/master/Casks/caffeine.rb

  Updating/Upgrading Casks

  Since the homebrew-cask repository is a Homebrew Tap, you’ll pull down the latest Casks every time you issue the regular Homebrew command brew update.

  When a new version homebrew-cask is released, it will appear in the output of brew outdated after running brew update. You can upgrade it via the normal Homebrew brew upgrade workflow:

  $ brew update && brew upgrade brew-cask && brew cleanup && brew cask cleanup

  Additional Taps (optional)

  The primary homebrew-cask Tap includes most of the Casks that a typical user will be interested in. There are a few additional Taps where we store different kinds of Casks.

  Tap name 	description
  caskroom/versions 	contains alternate versions of Casks (e.g. betas, nightly releases, old versions)

  caskroom/fonts 	contains Casks that install fonts, which are kept separate so we can educate users about the different licensing landscape around font installation/usage

  caskroom/unofficial 	contains Casks that install unofficial builds or forks

  $ brew tap <tap_name>

  after which, Casks from the new Tap will be available to search or install just like Casks from the main Tap. brew update will automatically keep your new Tap up to date.

  You may also specify a fully-qualified Cask token (which includes the Tap) for any brew cask command. This will implicitly add the Tap if you have not previously added it with brew tap:

  $ brew cask install caskroom/fonts/font-symbola

  Options

  brew cask accepts a number of options:

      --version: print version and exit
      --debug: output debug information
      --no-binaries: skip symlinking executable binaries into /usr/local/bin

  Advanced searching

  $ brew cask search '/^google.c[a-z]rome$/'
  google-chrome

  brew cask search font | sed '/Partial/d' | xargs brew cask info | grep http | xargs open

## OUTRO 1m
